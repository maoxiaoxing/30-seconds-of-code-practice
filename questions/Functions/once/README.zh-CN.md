
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

确保函数只被调用一次。

- 利用闭包，使用标志' called '，并在函数第一次被调用时将其设置为' true '，防止它再次被调用。
- 为了允许函数的“this”上下文发生变化(例如在事件监听器中)，必须使用“function”关键字，并且提供的函数必须应用上下文。
- 允许使用rest/spread('…')操作符为函数提供任意数量的参数。

```js
const once = fn => {
  let called = false;
  return function(...args) {
    if (called) return;
    called = true;
    return fn.apply(this, args);
  };
};
```

```js
const startApp = function(event) {
  console.log(this, event); // document.body, MouseEvent
};
document.body.addEventListener('click', once(startApp));
// only runs `startApp` once upon click
```
