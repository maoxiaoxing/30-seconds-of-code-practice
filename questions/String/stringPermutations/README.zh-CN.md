
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

生成字符串的所有排列(包含重复的)。

- 使用递归。
- 对于给定字符串中的每个字母，创建其其余字母的所有部分排列。
- 使用`Array.prototype.map()`将字母与每个部分排列组合在一起。
- 使用 `Array.prototype.reduce()` 将所有的排列组合在一个数组中。
- 基本情况是`String.prototype.length` 等于`2`或`1`。
- ⚠️**WARNING**:每个字符的执行时间呈指数增长。超过8到10个字符将导致您的环境挂起，因为它试图解决所有不同的组合。

```js
const stringPermutations = str => {
  if (str.length <= 2) return str.length === 2 ? [str, str[1] + str[0]] : [str];
  return str
    .split('')
    .reduce(
      (acc, letter, i) =>
        acc.concat(
          stringPermutations(str.slice(0, i) + str.slice(i + 1)).map(
            val => letter + val
          )
        ),
      []
    );
};
```

```js
stringPermutations('abc'); // ['abc', 'acb', 'bac', 'bca', 'cab', 'cba']
```
