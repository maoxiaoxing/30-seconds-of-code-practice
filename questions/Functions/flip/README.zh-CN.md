
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将一个函数作为参数，然后将第一个参数放在最后。

-使用参数解构和带有可变参数的闭包。
-拼接第一个参数，使用spread操作符('…')，使其在应用其他参数之前成为最后一个参数。

```js
const flip = fn => (first, ...rest) => fn(...rest, first);
```

```js
let a = { name: 'John Smith' };
let b = {};
const mergeFrom = flip(Object.assign);
let mergePerson = mergeFrom.bind(null, a);
mergePerson(b); // == b
b = {};
Object.assign(b, a); // == b
```
