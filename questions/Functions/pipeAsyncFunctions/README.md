
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Performs left-to-right function composition for asynchronous functions.

- Use `Array.prototype.reduce()` and the spread operator (`...`) to perform function composition using `Promise.prototype.then()`.
- The functions can return a combination of normal values, `Promise`s or be `async`, returning through `await`.
- All functions must accept a single argument.

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
