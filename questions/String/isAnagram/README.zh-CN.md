
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查一个字符串是否是另一个字符串的变位词(不区分大小写，忽略空格、标点和特殊字符)。

- 使用' String.prototype.toLowerCase() '和' String.prototype.replace() '使用适当的正则表达式来删除不必要的字符。
- 使用' String.prototype.split() '， ' Array.prototype.sort() '和' Array.prototype.join() '对两个字符串进行规范化，然后检查它们的规范化形式是否相等。

```js
const isAnagram = (str1, str2) => {
  const normalize = str =>
    str
      .toLowerCase()
      .replace(/[^a-z0-9]/gi, '')
      .split('')
      .sort()
      .join('');
  return normalize(str1) === normalize(str2);
};
```

```js
isAnagram('iceman', 'cinema'); // true
```
