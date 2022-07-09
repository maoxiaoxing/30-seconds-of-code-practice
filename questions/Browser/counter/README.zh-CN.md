
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

为指定选择器创建具有指定范围、步长和持续时间的计数器。

- 检查`step`是否有正确的符号，并相应地更改它。
- 将`setInterval()`与 `Math.abs()`和`Math.floor()` 结合使用来计算每次绘制新文本的时间间隔。
- 使用`Document.querySelector()`，`Element.innerHTML`来更新所选元素的值。
- 省略第四个参数`step`，使用默认步长`1`。
- 省略第五个参数`duration`，使用默认持续时间`2000`ms。

```js
const counter = (selector, start, end, step = 1, duration = 2000) => {
  let current = start,
    _step = (end - start) * step < 0 ? -step : step,
    timer = setInterval(() => {
      current += _step;
      document.querySelector(selector).innerHTML = current;
      if (current >= end) document.querySelector(selector).innerHTML = end;
      if (current >= end) clearInterval(timer);
    }, Math.abs(Math.floor(duration / (end - start))));
  return timer;
};
```

```js
counter('#my-id', 1, 1000, 5, 2000);
// Creates a 2-second timer for the element with id="my-id"
```
