
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个函数，调用给定上下文的' fn '，可选地将任何额外提供的参数添加到参数前面。

-返回一个' function '，使用' function .prototype.apply() '将给定的' context '应用到' fn '。
-使用spread操作符('…')将任何额外提供的形参放在实参前面。

```js
const bind = (fn, context, ...boundArgs) => (...args) =>
  fn.apply(context, [...boundArgs, ...args]);
```

```js
function greet(greeting, punctuation) {
  return greeting + ' ' + this.user + punctuation;
}
const freddy = { user: 'fred' };
const freddyBound = bind(greet, freddy);
console.log(freddyBound('hi', '!')); // 'hi fred!'
```
