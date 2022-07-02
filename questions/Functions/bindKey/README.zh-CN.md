
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个函数，该函数在对象的给定键处调用该方法，可选地将提供的任何附加参数添加到参数前面。
返回一个' function '，使用' function .prototype.apply() '将' context[fn] '绑定到' context '。

-使用spread操作符('…')将任何额外提供的形参放在实参前面。

```js
const bindKey = (context, fn, ...boundArgs) => (...args) =>
  context[fn].apply(context, [...boundArgs, ...args]);
```

```js
const freddy = {
  user: 'fred',
  greet: function(greeting, punctuation) {
    return greeting + ' ' + this.user + punctuation;
  }
};
const freddyBound = bindKey(freddy, 'greet');
console.log(freddyBound('hi', '!')); // 'hi fred!'
```
