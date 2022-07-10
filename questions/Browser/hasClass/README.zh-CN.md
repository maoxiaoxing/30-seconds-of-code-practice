
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查给定的元素是否具有指定的类。

- 使用 `Element.classList`和`DOMTokenList.contains()`来检查元素是否有指定的类。

```js
const hasClass = (el, className) => el.classList.contains(className);
```

```js
hasClass(document.querySelector('p.special'), 'special'); // true
```
