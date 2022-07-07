
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查字符串是否为小写。

- 使用' string .prototype. tolowercase() '将给定的字符串转换为小写，并与原始字符串进行比较。

```js
const isLowerCase = str => str === str.toLowerCase();
```

```js
isLowerCase('abc'); // true
isLowerCase('a3@$'); // true
isLowerCase('Ab4'); // false
```
