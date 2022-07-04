
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

遍历一个回调函数' n '次。

- 使用' Function.prototype.call() '调用' fn ' n次或直到它返回' false '。
- 省略最后一个参数' context '，以使用一个' undefined '对象(或在非严格模式下的全局对象)。

```js
const times = (n, fn, context = undefined) => {
  let i = 0;
  while (fn.call(context, i) !== false && ++i < n) {}
};
```

```js
var output = '';
times(5, i => (output += i));
console.log(output); // 01234
```
