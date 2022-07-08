
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Alphabetically sorts the characters in a string.

- Use the spread operator (`...`), `Array.prototype.sort()` and  `String.prototype.localeCompare()` to sort the characters in `str`.
- Recombine using `String.prototype.join()`.

```js
const sortCharactersInString = str =>
  [...str].sort((a, b) => a.localeCompare(b)).join('');
```

```js
sortCharactersInString('cabbage'); // 'aabbceg'
```