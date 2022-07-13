
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

深度冻结一个对象。

- 使用`Object.keys()`获取传递对象的所有属性，`Array.prototype.forEach()`迭代它们。
- 递归地对所有属性调用`Object.freeze()`，必要时应用`deepFreeze()`。
- 最后，使用`Object.freeze()`来冻结给定的对象。

```js
const deepFreeze = obj => {
  Object.keys(obj).forEach(prop => {
    if (typeof obj[prop] === 'object') deepFreeze(obj[prop]);
  });
  return Object.freeze(obj);
};
```

```js
'use strict';

const val = deepFreeze([1, [2, 3]]);

val[0] = 3; // not allowed
val[1][0] = 4; // not allowed as well
```
