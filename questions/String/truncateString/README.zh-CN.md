
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将字符串截断到指定长度。

- 确定是否`String.prototype.length`大于`num`。
- 返回被截断为所需长度的字符串，带有`…`追加到原始字符串的末尾。

```js
const truncateString = (str, num) =>
  str.length > num ? str.slice(0, num > 3 ? num - 3 : num) + '...' : str;
```

```js
truncateString('boomerang', 7); // 'boom...'
```
