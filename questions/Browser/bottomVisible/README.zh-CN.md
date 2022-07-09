
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查页面底部是否可见。

- 使用`Window.scrollY`, `Element.scrollHeight` and `Element.clientHeight`来确定页面底部是否可见。

```js
const bottomVisible = () =>
  document.documentElement.clientHeight + window.scrollY >=
  (document.documentElement.scrollHeight ||
    document.documentElement.clientHeight);
```

```js
bottomVisible(); // true
```
