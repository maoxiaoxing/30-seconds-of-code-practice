
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将逗号分隔值(CSV)字符串转换为2D数组。

- 使用' Array.prototype.indexOf() '来查找第一个换行符(' \n ')。
- 如果' omitFirstRow '为' true '，使用' Array.prototype.slice() '来删除第一行(标题行)。
- 使用' String.prototype.split() '为每一行创建一个字符串。
- 使用' String.prototype.split() '来分隔每行中的值，使用提供的'分隔符'。
- 省略第二个参数' delimiter '，使用默认的分隔符'，'。
- 省略第三个参数' omitFirstRow '，以包含CSV字符串的第一行(标题行)。

```js
const CSVToArray = (data, delimiter = ',', omitFirstRow = false) =>
  data
    .slice(omitFirstRow ? data.indexOf('\n') + 1 : 0)
    .split('\n')
    .map(v => v.split(delimiter));
```

```js
CSVToArray('a,b\nc,d'); // [['a', 'b'], ['c', 'd']];
CSVToArray('a;b\nc;d', ';'); // [['a', 'b'], ['c', 'd']];
CSVToArray('col1,col2\na,b\nc,d', ',', true); // [['a', 'b'], ['c', 'd']];
```
