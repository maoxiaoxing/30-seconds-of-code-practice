
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建调用所提供函数的函数，该函数的参数按指定索引排列。

-使用' Array.prototype.map() '根据'索引'重新排序参数。
-使用扩展操作符('…')将转换后的参数传递给' fn '。

```js
const rearg = (fn, indexes) => (...args) => fn(...indexes.map(i => args[i]));
```

```js
var rearged = rearg(
  function(a, b, c) {
    return [a, b, c];
  },
  [2, 0, 1]
);
rearged('b', 'c', 'a'); // ['a', 'b', 'c']
```
