
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

使用迭代器函数和初始值构建数组。

- 使用' while '循环和' Array.prototype.push() '反复调用函数，直到它返回' false '。
- 迭代器函数接受一个参数(' seed ')，必须返回一个包含两个元素的数组([' value '， ' nextSeed '])或' false '来终止。

```js
const unfold = (fn, seed) => {
  let result = [],
    val = [null, seed];
  while ((val = fn(val[1]))) result.push(val[0]);
  return result;
};
```

```js
var f = n => (n > 50 ? false : [-n, n + 10]);
unfold(f, 10); // [-10, -20, -30, -40, -50]
```
