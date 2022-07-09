
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将给定的数组元素转换为`<li>`标记，并将其附加到给定id的列表中。

- 使用`Array.prototype.map()`和`Document.querySelector()`创建html标记列表。

```js
const arrayToHTMLList = (arr, listID) =>
  document.querySelector(`#${listID}`).innerHTML += arr
    .map(item => `<li>${item}</li>`)
    .join('');
```

```js
arrayToHTMLList(['item 1', 'item 2'], 'myListID');
```
