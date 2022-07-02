
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

尝试使用提供的参数调用函数，返回结果或捕获的错误对象。
使用“try…”块返回函数的结果或适当的错误。

-如果捕获的对象不是一个' Error '，使用它创建一个新的' Error '。

```js
const attempt = (fn, ...args) => {
  try {
    return fn(...args);
  } catch (e) {
    return e instanceof Error ? e : new Error(e);
  }
};
```

```js
var elements = attempt(function(selector) {
  return document.querySelectorAll(selector);
}, '>_>');
if (elements instanceof Error) elements = []; // elements = []
```
