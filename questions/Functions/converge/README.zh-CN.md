
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

接受一个收敛函数和一个分支函数列表，并返回一个函数，该函数将每个分支函数应用于参数，分支函数的结果作为参数传递给收敛函数。

- 使用' Array.prototype.map() '和' function .prototype.apply() '将每个函数应用到给定的参数。
- 使用扩展操作符('…')调用'收敛'与所有其他函数的结果。

```js
const converge = (converger, fns) => (...args) =>
  converger(...fns.map(fn => fn.apply(null, args)));
```

```js
const average = converge((a, b) => a / b, [
  arr => arr.reduce((a, v) => a + v, 0),
  arr => arr.length
]);
average([1, 2, 3, 4, 5, 6, 7]); // 4
```
