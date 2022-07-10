
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

返回当前页面的滚动位置。

- 使用 `Window.pageXOffset`和 `Window.pageYOffset`，如果它们被定义，否则`Element.scrollLeft` 和 `Element.scrollTop`。
- 省略单个参数`el`来使用全局的`Window`对象。

```js
const getScrollPosition = (el = window) => ({
  x: el.pageXOffset !== undefined ? el.pageXOffset : el.scrollLeft,
  y: el.pageYOffset !== undefined ? el.pageYOffset : el.scrollTop
});
```

```js
getScrollPosition(); // {x: 0, y: 200}
```
