
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

在指定元素的末尾插入一个HTML字符串。

- 使用`Element.insertAdjacentHTML()`的位置为`'afterend'`来解析`htmlString`，并将其插入到`el`的结尾处。

```js
const insertAfter = (el, htmlString) =>
  el.insertAdjacentHTML('afterend', htmlString);
```

```js
insertAfter(document.getElementById('myId'), '<p>after</p>');
// <div id="myId">...</div> <p>after</p>
```
