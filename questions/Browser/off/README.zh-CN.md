
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

从元素中移除事件监听器。

- 使用`EventTarget.removeEventListener()`从元素中删除事件监听器。
- 省略第四个参数`opts`来使用`false`，或者根据添加事件监听器时使用的选项指定它。

```js
const off = (el, evt, fn, opts = false) =>
  el.removeEventListener(evt, fn, opts);
```

```js
const fn = () => console.log('!');
document.body.addEventListener('click', fn);
off(document.body, 'click', fn); // no longer logs '!' upon clicking on the page
```
