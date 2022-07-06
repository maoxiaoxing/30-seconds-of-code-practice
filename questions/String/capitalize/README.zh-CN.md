
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将字符串的第一个字母大写。

- 使用数组解构和' string. prototype. touppercase() '来将字符串的第一个字母大写。
- 使用' Array.prototype.join() '将大写的' first '和'…其他的角色。
- 省略' lowerRest '参数以保持字符串的其余部分不变，或将其设置为' true '以转换为小写。

```js
const capitalize = ([first, ...rest], lowerRest = false) =>
  first.toUpperCase() +
  (lowerRest ? rest.join('').toLowerCase() : rest.join(''));
```

```js
capitalize('fooBar'); // 'FooBar'
capitalize('fooBar', true); // 'Foobar'
```
