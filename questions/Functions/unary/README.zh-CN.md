
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个至多接受一个参数的函数，忽略任何其他参数。

-调用提供的函数' fn '，只提供第一个参数。

```js
const unary = fn => val => fn(val);
```

```js
['6', '8', '10'].map(unary(parseInt)); // [6, 8, 10]
```
