
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

检查数组中的所有元素是否相等。

-使用' array .prototype.every() '来检查数组的所有元素是否与第一个元素相同。
-数组中的元素使用严格比较操作符进行比较，不考虑“NaN”自不等。

```js
const allEqual = arr => arr.every(val => val === arr[0]);
```

```js
allEqual([1, 2, 3, 4, 5, 6]); // false
allEqual([1, 1, 1, 1]); // true
```
