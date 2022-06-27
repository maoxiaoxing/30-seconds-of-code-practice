
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查所提供的谓词函数是否为集合中的所有元素返回' true '。

-使用' Array.prototype.every() '来测试集合中的所有元素是否基于' fn '返回' true '。
-省略第二个参数' fn '，默认使用' Boolean '。

```js
all([4, 2, 3], x => x > 1); // true
all([1, 2, 3]); // true
```
