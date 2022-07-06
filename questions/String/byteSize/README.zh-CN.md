
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

返回以字节为单位的字符串长度。

- 将给定的字符串转换为[' Blob ' Object](https://developer.mozilla.org/en-US/docs/Web/API/Blob)。
- 使用`Blob.size`获取字符串的长度(以字节为单位)。

```js
const byteSize = str => new Blob([str]).size;
```

```js
byteSize('😀'); // 4
byteSize('Hello World'); // 11
```
