
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

记录函数名。

- 使用' console.debug() '和被传递函数的' name '属性将函数名记录到控制台的' debug '通道。
- 返回给定函数' fn '。

```js
const functionName = fn => (console.debug(fn.name), fn);
```

```js
let m = functionName(Math.max)(5, 6);
// max (logged in debug channel of console)
// m = 6
```
