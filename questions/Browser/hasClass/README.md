
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Checks if the given element has the specified class.

- Use `Element.classList` and `DOMTokenList.contains()` to check if the element has the specified class.

```js
const hasClass = (el, className) => el.classList.contains(className);
```

```js
hasClass(document.querySelector('p.special'), 'special'); // true
```
