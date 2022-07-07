
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

使用对给定字符串中的每个字符调用所提供的函数的结果创建一个新字符串。

- 使用' String.prototype.split() '和' Array.prototype.map() '为' str '中的每个字符调用所提供的函数' fn '。
- 使用' array .prototype.join() '将数组中的字符重新组合成一个字符串。
- 回调函数' fn '有三个参数(当前字符，当前字符的索引和被调用的字符串' mapString ')。

```js
const mapString = (str, fn) =>
  str
    .split('')
    .map((c, i) => fn(c, i, str))
    .join('');
```

```js
mapString('lorem ipsum', c => c.toUpperCase()); // 'LOREM IPSUM'
```
