
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

用指定的掩码字符替换除最后一个“num”以外的所有字符。

- 使用' String.prototype.slice() '来获取将保持未屏蔽的字符部分。
- 使用' string . padstart() '用' mask '字符填充字符串的开始，直到原始长度。
- 如果' num '为负数，则显示的字符将位于字符串的开头。
- 省略第二个参数' num '，以保持默认的' 4 '字符不被屏蔽。
- 省略第三个参数“mask”，以使用默认字符“*”作为掩码。

```js
const mask = (cc, num = 4, mask = '*') =>
  `${cc}`.slice(-num).padStart(`${cc}`.length, mask);
```

```js
mask(1234567890); // '******7890'
mask(1234567890, 3); // '*******890'
mask(1234567890, -4, '$'); // '$$$$567890'
```
