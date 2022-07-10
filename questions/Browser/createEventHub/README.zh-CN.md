
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个发布/订阅([publish-subscribe](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern))事件中心，使用`emit`， `on`和`off`方法。

- 使用 `Object.create()` 和`null`参数创建一个空的`hub`对象，不从`Object.prototype`继承属性。
- 对于`emit`，根据`event`参数解析处理程序数组，然后使用`Array.prototype.forEach()`通过传入数据作为参数来运行每个处理程序。
- 对于`on`，如果事件不存在，则为其创建一个数组，然后使用 `Array.prototype.push()`添加处理程序
- 到数组。
- 对于`off`，使用`Array.prototype.findIndex()`在事件数组中找到处理程序的索引，并使用`Array.prototype.splice()`删除它。

```js
const createEventHub = () => ({
  hub: Object.create(null),
  emit(event, data) {
    (this.hub[event] || []).forEach(handler => handler(data));
  },
  on(event, handler) {
    if (!this.hub[event]) this.hub[event] = [];
    this.hub[event].push(handler);
  },
  off(event, handler) {
    const i = (this.hub[event] || []).findIndex(h => h === handler);
    if (i > -1) this.hub[event].splice(i, 1);
    if (this.hub[event].length === 0) delete this.hub[event];
  }
});
```

```js
const handler = data => console.log(data);
const hub = createEventHub();
let increment = 0;

// Subscribe: listen for different types of events
hub.on('message', handler);
hub.on('message', () => console.log('Message event fired'));
hub.on('increment', () => increment++);

// Publish: emit events to invoke all handlers subscribed to them, passing the data to them as an argument
hub.emit('message', 'hello world'); // logs 'hello world' and 'Message event fired'
hub.emit('message', { hello: 'world' }); // logs the object and 'Message event fired'
hub.emit('increment'); // `increment` variable is now 1

// Unsubscribe: stop a specific handler from listening to the 'message' event
hub.off('message', handler);
```
