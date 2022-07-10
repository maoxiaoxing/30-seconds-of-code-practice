
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查`父`元素是否包含`子`元素。

- 检查`parent`和`child`不是同一个元素。

- 使用`Node.contains()`来检查`父`元素是否包含`子`元素。

```js
const elementContains = (parent, child) =>
  parent !== child && parent.contains(child);
```

```js
elementContains(
  document.querySelector('head'),
  document.querySelector('title')
);
// true
elementContains(document.querySelector('body'), document.querySelector('body'));
// false
```
