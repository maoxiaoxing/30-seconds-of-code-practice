
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

柯里化一个函数。

- 使用递归。
- 如果提供的参数(' args ')数量足够，调用传递的函数' fn '。
- 否则，使用' function .prototype.bind() '来返回一个curry过的函数' fn '，该函数需要其他参数。
- 如果你想curry一个函数，接受一个可变数量的参数(可变参数函数，例如。' Math.min() '))，你可以选择将参数的数量传递给第二个参数' arity '。

```js
const curry = (fn, arity = fn.length, ...args) =>
  arity <= args.length ? fn(...args) : curry.bind(null, fn, arity, ...args);
```

```js
curry(Math.pow)(2)(10); // 1024
curry(Math.min, 3)(10)(50)(2); // 2
```
