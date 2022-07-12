
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Toggles a class for an HTML element.

- Use `Element.classList` and `DOMTokenList.toggle()` to toggle the specified class for the element.

```js
const toggleClass = (el, className) => el.classList.toggle(className);
```

```js
toggleClass(document.querySelector('p.special'), 'special');
// The paragraph will not have the 'special' class anymore
```
