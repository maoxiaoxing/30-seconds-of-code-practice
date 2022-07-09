
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将字符串转换为蛇形大小写。

- 使用`String.prototype.match()`使用适当的regexp将字符串拆分为单词。
- 使用`Array.prototype.map()`， `Array.prototype.slice()`， `Array.prototype.join()`和`String.prototype.toLowerCase()`来组合它们，并添加`_`作为分隔符。

```js
const toSnakeCase = str =>
  str &&
  str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    .map(x => x.toLowerCase())
    .join('_');
```

```js
toSnakeCase('camelCase'); // 'camel_case'
toSnakeCase('some text'); // 'some_text'
toSnakeCase('some-mixed_string With spaces_underscores-and-hyphens');
// 'some_mixed_string_with_spaces_underscores_and_hyphens'
toSnakeCase('AllThe-small Things'); // 'all_the_small_things'
toSnakeCase('IAmEditingSomeXMLAndHTML');
// 'i_am_editing_some_xml_and_html'
```
