
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

切换HTML元素的类。

- 使用`Element.classList` 和`DOMTokenList.toggle()`来切换元素的指定类。

```js
const toggleClass = (el, className) => el.classList.toggle(className);
```

```js
toggleClass(document.querySelector('p.special'), 'special');
// The paragraph will not have the 'special' class anymore
```
