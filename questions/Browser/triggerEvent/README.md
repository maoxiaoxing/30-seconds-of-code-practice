
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Triggers a specific event on a given element, optionally passing custom data.

- Use the `CustomEvent` constructor to create an event from the specified `eventType` and details.
- Use `EventTarget.dispatchEvent()` to trigger the newly created event on the given element.
- Omit the third argument, `detail`, if you do not want to pass custom data to the triggered event.

```js
const triggerEvent = (el, eventType, detail) =>
  el.dispatchEvent(new CustomEvent(eventType, { detail }));
```

```js
triggerEvent(document.getElementById('myId'), 'click');
triggerEvent(document.getElementById('myId'), 'click', { username: 'bob' });
```
