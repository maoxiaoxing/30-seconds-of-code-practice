
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

在每个动画帧上调用提供的回调函数。

- 使用递归。
- 假设`running`为 `true`，继续调用`Window.requestAnimationFrame()`，它会调用提供的回调函数。
- 返回一个具有 `start` 和 `stop` 两个方法的对象，以允许手动控制录制。
- 省略第二个参数`autoStart`，以便在调用函数时隐式调用`start`。

```js
const recordAnimationFrames = (callback, autoStart = true) => {
  let running = false,
    raf;
  const stop = () => {
    if (!running) return;
    running = false;
    cancelAnimationFrame(raf);
  };
  const start = () => {
    if (running) return;
    running = true;
    run();
  };
  const run = () => {
    raf = requestAnimationFrame(() => {
      callback();
      if (running) run();
    });
  };
  if (autoStart) start();
  return { start, stop };
};
```

```js
const cb = () => console.log('Animation frame fired');
const recorder = recordAnimationFrames(cb);
// logs 'Animation frame fired' on each animation frame
recorder.stop(); // stops logging
recorder.start(); // starts again
const recorder2 = recordAnimationFrames(cb, false);
// `start` needs to be explicitly called to begin recording frames
```
