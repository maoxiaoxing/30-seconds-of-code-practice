
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将字符串的第一个字母改大写。

- 使用数组解构和' String.prototype.toLowerCase() '来将第一个字母改大，'…rest '获取首字母后的字符数组，然后' array .prototype.join() '使其再次成为字符串。
- 省略' upperRest '参数以保持字符串的其余部分不变，或将其设置为' true '以转换为大写。

```js
const decapitalize = ([first, ...rest], upperRest = false) =>
  first.toLowerCase() +
  (upperRest ? rest.join('').toUpperCase() : rest.join(''));
```

```js
decapitalize('FooBar'); // 'fooBar'
decapitalize('FooBar', true); // 'fOOBAR'
```
