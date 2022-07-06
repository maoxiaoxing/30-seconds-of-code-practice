
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Returns the length of a string in bytes.

- Convert a given string to a [`Blob` Object](https://developer.mozilla.org/en-US/docs/Web/API/Blob).
- Use `Blob.size` to get the length of the string in bytes.

```js
const byteSize = str => new Blob([str]).size;
```

```js
byteSize('😀'); // 4
byteSize('Hello World'); // 11
```
