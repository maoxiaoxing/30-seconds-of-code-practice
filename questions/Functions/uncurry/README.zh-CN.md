
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

取消一个深度为' n '的函数。

- 返回可变参数函数。
- 在提供的参数上使用' Array.prototype.reduce() '来调用该函数的后续curry级别。
- 如果提供的参数的“长度”小于“n”则抛出错误。
- 否则，使用' Array.prototype.slice() '调用' fn '并使用适当数量的参数。
- 省略第二个参数' n '，以解压缩到深度' 1 '。

```js
const uncurry = (fn, n = 1) => (...args) => {
  const next = acc => args => args.reduce((x, y) => x(y), acc);
  if (n > args.length) throw new RangeError('Arguments too few!');
  return next(fn)(args.slice(0, n));
};
```

```js
const add = x => y => z => x + y + z;
const uncurriedAdd = uncurry(add, 3);
uncurriedAdd(1, 2, 3); // 6
```
