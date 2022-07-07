
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

缩进提供的字符串中的每一行。

- 使用' String.prototype.replace() '和一个正则表达式在每行开始添加由' indent ' ' count '指定的字符。
- 省略第三个参数' indent '，以使用默认的缩进字符' '。

```js
const indentString = (str, count, indent = ' ') =>
  str.replace(/^/gm, indent.repeat(count));
```

```js
indentString('Lorem\nIpsum', 2); // '  Lorem\n  Ipsum'
indentString('Lorem\nIpsum', 2, '_'); // '__Lorem\n__Ipsum'
```
