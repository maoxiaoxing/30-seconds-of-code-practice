
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

按字母顺序对字符串中的字符进行排序。

- 使用spread操作符(`…`)、`Array.prototype.sort()`和`String.prototype.localeCompare()`对`str`中的字符进行排序。
- 使用`String.prototype.join()`重新组合。



```js
const sortCharactersInString = str =>
  [...str].sort((a, b) => a.localeCompare(b)).join('');
```

```js
sortCharactersInString('cabbage'); // 'aabbceg'
```