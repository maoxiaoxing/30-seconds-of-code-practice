
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

设置指定HTML元素的CSS规则的值。

- 使用 `ElementCSSInlineStyle.style` 将指定元素的CSS规则的值设置为`val`。

```js
const setStyle = (el, rule, val) => (el.style[rule] = val);
```

```js
setStyle(document.querySelector('p'), 'font-size', '20px');
// The first <p> element on the page will have a font-size of 20px
```
