
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查给定字符串是否为回文。

- 将字符串规范化为`String.prototype.tolowercase()`，并使用`String.prototype.replace()`来移除其中的非字母数字字符。
- 使用扩展操作符(`…`)将规范化字符串拆分为单个字符。
- 使用`Array.prototype.reverse()`， `String.prototype.join()`并将结果与规范化字符串进行比较。

```js
const palindrome = str => {
  const s = str.toLowerCase().replace(/[\W_]/g, '');
  return s === [...s].reverse().join('');
};
```

```js
palindrome('taco cat'); // true
```
