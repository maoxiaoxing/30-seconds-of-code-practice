
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

返回一个函数，该函数接受一个参数，如果参数为真，则运行回调函数，如果参数为假，则返回该参数。

- 返回一个函数，该函数需要一个值' x '，该值基于' pred '返回适当的值。

```js
const when = (pred, whenTrue) => x => (pred(x) ? whenTrue(x) : x);
```

```js
const doubleEvenNumbers = when(x => x % 2 === 0, x => x * 2);
doubleEvenNumbers(2); // 4
doubleEvenNumbers(1); // 1
```
