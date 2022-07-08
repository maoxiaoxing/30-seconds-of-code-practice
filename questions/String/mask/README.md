
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Replaces all but the last `num` of characters with the specified mask character.

- Use `String.prototype.slice()` to grab the portion of the characters that will remain unmasked.
- Use `String.padStart()` to fill the beginning of the string with the `mask` character up to the original length.
- If `num` is negative, the unmasked characters will be at the start of the string.
- Omit the second argument, `num`, to keep a default of `4` characters unmasked.
- Omit the third argument, `mask`, to use a default character of `'*'` for the mask.

```js
const mask = (cc, num = 4, mask = '*') =>
  `${cc}`.slice(-num).padStart(`${cc}`.length, mask);
```

```js
mask(1234567890); // '******7890'
mask(1234567890, 3); // '*******890'
mask(1234567890, -4, '$'); // '$$$$567890'
```
