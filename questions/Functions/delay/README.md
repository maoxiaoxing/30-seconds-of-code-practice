
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Invokes the provided function after `ms` milliseconds.
- Use `setTimeout()` to delay execution of `fn`.
- Use the spread (`...`) operator to supply the function with an arbitrary number of arguments.

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
