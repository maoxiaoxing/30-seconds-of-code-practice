
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将字符串转换为烤肉串大小写。

- 使用`String.prototype.match()`使用适当的regexp将字符串拆分为单词。
- 使用`Array.prototype.map()`， `Array.prototype.join()`和`String.prototype.toLowerCase()`来组合它们，添加`-`作为分隔符。

```js
const toKebabCase = str =>
  str &&
  str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    .map(x => x.toLowerCase())
    .join('-');
```

```js
toKebabCase('camelCase'); // 'camel-case'
toKebabCase('some text'); // 'some-text'
toKebabCase('some-mixed_string With spaces_underscores-and-hyphens');
// 'some-mixed-string-with-spaces-underscores-and-hyphens'
toKebabCase('AllThe-small Things'); // 'all-the-small-things'
toKebabCase('IAmEditingSomeXMLAndHTML');
// 'i-am-editing-some-xml-and-html'
```
