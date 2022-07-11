
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查页面的浏览器选项卡是否集中。

- 使用 `Document.hidden` 属性，由[Page Visibility API](https://developer.mozilla.org/en-US/docs/Web/API/Page_Visibility_API)引入，用于检查页面的浏览器选项卡是否可见或隐藏。

```js
const isBrowserTabFocused = () => !document.hidden;
```

```js
isBrowserTabFocused(); // true
```
