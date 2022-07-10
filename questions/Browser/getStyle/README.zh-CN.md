
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

---

获取指定元素的CSS规则的值。

- 使用`Window.getComputedStyle()`获取指定元素的CSS规则的值。

```js
const getStyle = (el, ruleName) => getComputedStyle(el)[ruleName];
```

```js
getStyle(document.querySelector('p'), 'font-size'); // '16px'
```
