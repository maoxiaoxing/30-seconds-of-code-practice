
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Creates a debounced function that delays invoking the provided function until at least `ms` milliseconds have elapsed since its last invocation.

- Each time the debounced function is invoked, clear the current pending timeout with `clearTimeout()`. Use `setTimeout()` to create a new timeout that delays invoking the function until at least `ms` milliseconds have elapsed.
- Use `Function.prototype.apply()` to apply the `this` context to the function and provide the necessary arguments.
- Omit the second argument, `ms`, to set the timeout at a default of `0` ms.

```js
const debounce = (fn, ms = 0) => {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn.apply(this, args), ms);
  };
};
```

```js
window.addEventListener(
  'resize',
  debounce(() => {
    console.log(window.innerWidth);
    console.log(window.innerHeight);
  }, 250)
); // Will log the window dimensions at most every 250ms
```
