
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

为异步函数执行从左到右的函数组合。

-使用' Array.prototype.reduce() '和扩展操作符('…')来使用' Promise.prototype.then() '执行函数组合。
-函数可以返回正常值的组合，' Promise '或' async '，通过' await '返回。
-所有函数必须接受一个参数。

```js
const pipeAsyncFunctions = (...fns) =>
  arg => fns.reduce((p, f) => p.then(f), Promise.resolve(arg));
```

```js
const sum = pipeAsyncFunctions(
  x => x + 1,
  x => new Promise(resolve => setTimeout(() => resolve(x + 2), 1000)),
  x => x + 3,
  async x => (await x) + 4
);
(async() => {
  console.log(await sum(5)); // 15 (after one second)
})();
```
