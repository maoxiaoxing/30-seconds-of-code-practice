
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将所有给定的URL段连接在一起，然后对结果URL进行规范化。

- 使用`String.prototype.join()`来组合URL段。
- 使用一系列的`String.prototype.replace()`调用各种regexp来规范化结果URL(删除双斜杠，为协议添加适当的斜杠，在参数之前删除斜杠，将参数与`'&'` 结合并规范化第一个参数分隔符)。

```js
const URLJoin = (...args) =>
  args
    .join('/')
    .replace(/[\/]+/g, '/')
    .replace(/^(.+):\//, '$1://')
    .replace(/^file:/, 'file:/')
    .replace(/\/(\?|&|#[^!])/g, '$1')
    .replace(/\?/g, '&')
    .replace('&', '?');
```

```js
URLJoin('http://www.google.com', 'a', '/b/cd', '?foo=123', '?bar=foo');
// 'http://www.google.com/a/b/cd?foo=123&bar=foo'
```
