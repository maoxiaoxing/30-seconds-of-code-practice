
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将接受数组的函数更改为可变参数函数。

-给定一个函数，返回一个闭包，将所有输入收集到一个数组接受函数。

```js
const collectInto = fn => (...args) => fn(args);
```

```js
const Pall = collectInto(Promise.all.bind(Promise));
let p1 = Promise.resolve(1);
let p2 = Promise.resolve(2);
let p3 = new Promise(resolve => setTimeout(resolve, 2000, 3));
Pall(p1, p2, p3).then(console.log); // [1, 2, 3] (after about 2 seconds)
```
