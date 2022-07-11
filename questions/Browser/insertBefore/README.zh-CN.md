
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

在指定元素开始之前插入HTML字符串。

- 使用`Element.insertAdjacentHTML()`的位置为`'beforebegin'`来解析`htmlString`，并插入在`el`之前。

```js
const insertBefore = (el, htmlString) =>
  el.insertAdjacentHTML('beforebegin', htmlString);
```

```js
insertBefore(document.getElementById('myId'), '<p>before</p>');
// <p>before</p> <div id="myId">...</div>
```
