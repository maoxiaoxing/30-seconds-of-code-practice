
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

从字符串创建元素(不将其附加到文档)。
如果给定的字符串包含多个元素，则只返回第一个元素。

- 使用 `Document.createElement()`创建新元素。
- 使用 `Element.innerHTML` 将其内部HTML设置为作为参数提供的字符串。
- 使用 `Element.firstElementChild` 返回字符串的元素版本。

```js
const createElement = str => {
  const el = document.createElement('div');
  el.innerHTML = str;
  return el.firstElementChild;
};
```

```js
const el = createElement(
  `<div class="container">
    <p>Hello!</p>
  </div>`
);
console.log(el.className); // 'container'
```
