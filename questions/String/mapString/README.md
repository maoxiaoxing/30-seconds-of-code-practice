
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Creates a new string with the results of calling a provided function on every character in the given string.

- Use `String.prototype.split()` and `Array.prototype.map()` to call the provided function, `fn`, for each character in `str`.
- Use `Array.prototype.join()` to recombine the array of characters into a string.
- The callback function, `fn`, takes three arguments (the current character, the index of the current character and the string `mapString` was called upon).

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
