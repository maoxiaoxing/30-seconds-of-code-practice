
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个函数，该函数调用已转换参数的所提供的函数。

-使用' Array.prototype.map() '对' args '应用' transforms '，并结合spread操作符('…')将转换后的参数传递给' fn '。

```js
const overArgs = (fn, transforms) =>
  (...args) => fn(...args.map((val, i) => transforms[i](val)));
```

```js
const square = n => n * n;
const double = n => n * 2;
const fn = overArgs((x, y) => [x, y], [square, double]);
fn(9, 3); // [81, 6]
```
