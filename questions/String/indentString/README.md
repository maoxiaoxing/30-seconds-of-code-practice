
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Indents each line in the provided string.

- Use `String.prototype.replace()` and a regular expression to add the character specified by `indent` `count` times at the start of each line.
- Omit the third argument, `indent`, to use a default indentation character of `' '`.

```js
const indentString = (str, count, indent = ' ') =>
  str.replace(/^/gm, indent.repeat(count));
```

```js
indentString('Lorem\nIpsum', 2); // '  Lorem\n  Ipsum'
indentString('Lorem\nIpsum', 2, '_'); // '__Lorem\n__Ipsum'
```
