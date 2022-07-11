
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Creates a hash for a value using the [SHA-256](https://en.wikipedia.org/wiki/SHA-2) algorithm.
Returns a promise.

- Use the [SubtleCrypto](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto) API to create a hash for the given value.
- Create a new `TextEncoder` and use it to encode `val`. Pass its value to `SubtleCrypto.digest()` to generate a digest of the given data.
- Use `DataView.prototype.getUint32()` to read data from the resolved `ArrayBuffer`.
- Convert the data to its hexadecimal representation using `Number.prototype.toString()`. Add the data to an array using `Array.prototype.push()`.
- Finally, use `Array.prototype.join()` to combine values in the array of `hexes` into a string.

```js
const hashBrowser = val =>
  crypto.subtle
    .digest('SHA-256', new TextEncoder('utf-8').encode(val))
    .then(h => {
      let hexes = [],
        view = new DataView(h);
      for (let i = 0; i < view.byteLength; i += 4)
        hexes.push(('00000000' + view.getUint32(i).toString(16)).slice(-8));
      return hexes.join('');
    });
```

```js
hashBrowser(
  JSON.stringify({ a: 'a', b: [1, 2, 3, 4], foo: { c: 'bar' } })
).then(console.log);
// '04aa106279f5977f59f9067fa9712afc4aedc6f5862a8defc34552d8c7206393'
```
