
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

在' ms '毫秒之后调用提供的函数。

- 使用' setTimeout() '来延迟' fn '的执行。
- 使用spread('…')操作符为函数提供任意数量的参数。

```js
const delay = (fn, ms, ...args) => setTimeout(fn, ms, ...args);
```

```js
delay(
  function(text) {
    console.log(text);
  },
  1000,
  'later'
); // Logs 'later' after one second.
```
