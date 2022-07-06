
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将逗号分隔值(CSV)字符串转换为2D对象数组。
字符串的第一行用作标题行。

- 使用' Array.prototype.indexOf() '来查找第一个换行符(' \n ')。
- 使用' Array.prototype.slice() '来删除第一行(标题行)，使用' String.prototype.split() '来将其分隔成值，使用提供的'分隔符'。
- 使用' String.prototype.split() '为每一行创建一个字符串。
- 使用' String.prototype.split() '来分隔每行中的值，使用提供的'分隔符'。
- 使用' Array.prototype.reduce() '为每一行的值创建一个对象，从标题行解析出键。
- 省略第二个参数' delimiter '，使用默认的分隔符'，'。

```js
const CSVToJSON = (data, delimiter = ',') => {
  const titles = data.slice(0, data.indexOf('\n')).split(delimiter);
  return data
    .slice(data.indexOf('\n') + 1)
    .split('\n')
    .map(v => {
      const values = v.split(delimiter);
      return titles.reduce(
        (obj, title, index) => ((obj[title] = values[index]), obj),
        {}
      );
    });
};
```

```js
CSVToJSON('col1,col2\na,b\nc,d');
// [{'col1': 'a', 'col2': 'b'}, {'col1': 'c', 'col2': 'd'}];
CSVToJSON('col1;col2\na;b\nc;d', ';');
// [{'col1': 'a', 'col2': 'b'}, {'col1': 'c', 'col2': 'd'}];
```
