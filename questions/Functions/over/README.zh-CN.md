
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个函数，该函数调用每个提供的函数，并使用它接收的参数返回结果。

-使用' Array.prototype.map() '和' function .prototype.apply() '将每个函数应用到给定的参数。

```js
const over = (...fns) => (...args) => fns.map(fn => fn.apply(null, args));
```

```js
const minMax = over(Math.min, Math.max);
minMax(1, 2, 3, 4, 5); // [1, 5]
```
