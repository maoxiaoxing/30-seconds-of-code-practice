
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

测量函数每秒执行的次数(hz/赫兹)。

- 使用' performance.now() '来获得迭代循环前后的毫秒差值，从而计算执行函数' iterations ' times所花费的时间。
- 通过将毫秒转换为秒并除以所经过的时间，返回每秒周期数。
- 省略第二个参数' iterations '，以使用默认的100个迭代。

```js
const hz = (fn, iterations = 100) => {
  const before = performance.now();
  for (let i = 0; i < iterations; i++) fn();
  return (1000 * iterations) / (performance.now() - before);
};
```

```js
const numbers = Array(10000).fill().map((_, i) => i);

const sumReduce = () => numbers.reduce((acc, n) => acc + n, 0);
const sumForLoop = () => {
  let sum = 0;
  for (let i = 0; i < numbers.length; i++) sum += numbers[i];
  return sum;
};

Math.round(hz(sumReduce)); // 572
Math.round(hz(sumForLoop)); // 4784
```
