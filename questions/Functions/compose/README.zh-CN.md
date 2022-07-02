
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

执行从右到左的函数组合。

-使用' Array.prototype.reduce() '来执行从右到左的函数组合。
-最后一个(最右的)函数可以接受一个或多个参数;其余函数必须是一元函数。

```js
const compose = (...fns) =>
  fns.reduce((f, g) => (...args) => f(g(...args)));
```

```js
const add5 = x => x + 5;
const multiply = (x, y) => x * y;
const multiplyAndAdd5 = compose(
  add5,
  multiply
);
multiplyAndAdd5(5, 2); // 15
```
