
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

如果字符串短于指定的“长度”，则在字符串的两边填充指定的字符。

- 使用' string. prototype. padstart() '和' string. prototype. padend() '填充给定字符串的两边。
- 省略第三个参数' char '，以使用空白字符作为默认填充字符。

```js
const pad = (str, length, char = ' ') =>
  str.padStart((str.length + length) / 2, char).padEnd(length, char);
```

```js
pad('cat', 8); // '  cat   '
pad(String(42), 6, '0'); // '004200'
pad('foobar', 3); // 'foobar'
```
