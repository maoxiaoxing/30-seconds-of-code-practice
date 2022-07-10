
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Returns the scroll position of the current page.

- Use `Window.pageXOffset` and `Window.pageYOffset` if they are defined, otherwise `Element.scrollLeft` and `Element.scrollTop`.
- Omit the single argument, `el`, to use the global `Window` object.

```js
const getScrollPosition = (el = window) => ({
  x: el.pageXOffset !== undefined ? el.pageXOffset : el.scrollLeft,
  y: el.pageYOffset !== undefined ? el.pageYOffset : el.scrollTop
});
```

```js
getScrollPosition(); // {x: 0, y: 200}
```
