
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查所提供的函数对于集合中的至少一个元素是否返回' true '。

- 使用' Array.prototype.some() '来测试集合中是否有任何元素根据' fn '返回' true '。
- 省略第二个参数' fn '，默认使用' Boolean '。

```js
const any = (arr, fn = Boolean) => arr.some(fn);
```

```js
any([0, 1, 2, 0], x => x >= 2); // true
any([0, 0, 1, 0]); // true
```
