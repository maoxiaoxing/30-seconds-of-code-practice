
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

反转一个字符串。

- 使用spread操作符(`…`)和`Array.prototype.reverse()`来反转字符串中字符的顺序。
- 使用`String.prototype.join()`组合字符来获得一个字符串。


```js
const reverseString = str => [...str].reverse().join('');
```

```js
reverseString('foobar'); // 'raboof'
```
