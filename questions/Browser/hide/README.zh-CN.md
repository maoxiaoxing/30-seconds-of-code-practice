
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

隐藏所有指定的元素。

- 使用spread操作符(`…`)和`Array.prototype.forEach()`对指定的每个元素应用`display: none`。

```js
const hide = (...el) => [...el].forEach(e => (e.style.display = 'none'));
```

```js
hide(...document.querySelectorAll('img')); // Hides all <img> elements on the page
```
