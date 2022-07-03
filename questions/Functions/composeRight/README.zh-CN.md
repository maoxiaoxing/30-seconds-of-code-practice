
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

执行从左到右的函数组合。

- 使用' Array.prototype.reduce() '来执行从左到右的函数组合。
- 第一个(最左边)函数可以接受一个或多个参数;其余函数必须是一元函数。

```js
const composeRight = (...fns) =>
  fns.reduce((f, g) => (...args) => g(f(...args)));
```

```js
const add = (x, y) => x + y;
const square = x => x * x;
const addAndSquare = composeRight(add, square);
addAndSquare(1, 2); // 9
```
