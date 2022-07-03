
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个防抖函数，该函数将延迟调用所提供的函数，直到自上次调用以来至少经过' ms '毫秒。

- 每次调用防抖函数时，使用' clearTimeout() '清除当前挂起的超时。使用' setTimeout() '创建一个新的超时，该超时将延迟调用该函数，直到至少' ms '毫秒过去。
- 使用' function .prototype.apply() '将' this '上下文应用到函数，并提供必要的参数。

- 省略第二个参数' ms '，将超时设置为默认的' 0 ' ms。

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
