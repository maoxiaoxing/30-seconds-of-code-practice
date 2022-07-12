
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

每当用户输入类型改变时(`mouse`或`touch`)运行回调。

- 使用两个事件监听器。
- 假设最初是`mouse`输入，并绑定一个`'touchstart'`事件监听器到文档。
- 在`'touchstart'`上，添加一个`'mousemove'`事件监听器来监听在20ms内连续触发的两个`'mousemove'`事件，使用`performance.now()`。
- 在这两种情况下都以输入类型作为参数运行回调。

```js
const onUserInputChange = callback => {
  let type = 'mouse',
    lastTime = 0;
  const mousemoveHandler = () => {
    const now = performance.now();
    if (now - lastTime < 20)
      (type = 'mouse'),
        callback(type),
        document.removeEventListener('mousemove', mousemoveHandler);
    lastTime = now;
  };
  document.addEventListener('touchstart', () => {
    if (type === 'touch') return;
    (type = 'touch'),
      callback(type),
      document.addEventListener('mousemove', mousemoveHandler);
  });
};
```

```js
onUserInputChange(type => {
  console.log('The user is now using', type, 'as an input method.');
});
```
