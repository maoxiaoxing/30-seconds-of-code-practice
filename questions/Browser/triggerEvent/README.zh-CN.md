
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

触发给定元素上的特定事件，可选地传递定制数据。

- 使用`CustomEvent` 构造函数从指定的`eventType` 和详细信息创建一个事件。
- 使用 `EventTarget.dispatchEvent()` 来触发给定元素上新创建的事件。
- 省略第三个参数`detail`，如果你不想传递自定义数据到触发事件。

```js
const triggerEvent = (el, eventType, detail) =>
  el.dispatchEvent(new CustomEvent(eventType, { detail }));
```

```js
triggerEvent(document.getElementById('myId'), 'click');
triggerEvent(document.getElementById('myId'), 'click', { username: 'bob' });
```
