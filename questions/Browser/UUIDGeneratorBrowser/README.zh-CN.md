
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

在浏览器中生成一个UUID。

- 使用`Crypto.getRandomValues()`生成一个UUID，与[RFC4122](https://www.ietf.org/rfc/rfc4122.txt)版本4兼容。
- 使用`Number.prototype.toString()`将其转换为一个正确的UUID(十六进制字符串)。

```js
const UUIDGeneratorBrowser = () =>
  ([1e7] + -1e3 + -4e3 + -8e3 + -1e11).replace(/[018]/g, c =>
    (
      c ^
      (crypto.getRandomValues(new Uint8Array(1))[0] & (15 >> (c / 4)))
    ).toString(16)
  );
```

```js
UUIDGeneratorBrowser(); // '7982fcfe-5721-4632-bede-6000885be57d'
```
