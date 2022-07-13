
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

为一个对象中所有未定义的属性赋值。

- 使用`Object.assign()`创建一个新的空对象，并复制原来的对象来保持键的顺序。
- 使用`Array.prototype.reverse()`和spread操作符(`…`)从左到右组合默认值。
- 最后，再次使用`obj`来覆盖原来有一个值的属性。

```js
const defaults = (obj, ...defs) =>
  Object.assign({}, obj, ...defs.reverse(), obj);
```

```js
defaults({ a: 1 }, { b: 2 }, { b: 6 }, { a: 3 }); // { a: 1, b: 2 }
```
