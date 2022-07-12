
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

显示所有指定的元素。

- 使用spread操作符(`…`)和`Array.prototype.forEach()`来清除每个指定元素的`display`属性。

```js
const show = (...el) => [...el].forEach(e => (e.style.display = ''));
```

```js
show(...document.querySelectorAll('img'));
// Shows all <img> elements on the page
```
