
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将异步函数转换为返回承诺。

-使用curry返回一个函数，返回一个调用原始函数的' Promise '。
-使用rest操作符('…')传入所有参数。
- **注意:**在节点8+中，可以使用[' util.promisify '](https://nodejs.org/api/util.html#util_util_promisify_original)。


```js
const promisify = func => (...args) =>
  new Promise((resolve, reject) =>
    func(...args, (err, result) => (err ? reject(err) : resolve(result)))
  );
```

```js
const delay = promisify((d, cb) => setTimeout(cb, d));
delay(2000).then(() => console.log('Hi!')); // Promise resolves after 2s
```
