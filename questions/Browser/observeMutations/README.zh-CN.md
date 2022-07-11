
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建一个新的`MutationObserver`，并为指定元素上的每个突变运行所提供的回调。

- 使用[`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)来观察给定元素的突变。
- 使用`Array.prototype.forEach()`对观察到的每个突变运行回调。
- 省略第三个参数`options`，使用默认的[options](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver#MutationObserverInit)(全部为`true`)。



```js
const observeMutations = (element, callback, options) => {
  const observer = new MutationObserver(mutations =>
    mutations.forEach(m => callback(m))
  );
  observer.observe(
    element,
    Object.assign(
      {
        childList: true,
        attributes: true,
        attributeOldValue: true,
        characterData: true,
        characterDataOldValue: true,
        subtree: true,
      },
      options
    )
  );
  return observer;
};
```

```js
const obs = observeMutations(document, console.log);
// Logs all mutations that happen on the page
obs.disconnect();
// Disconnects the observer and stops logging mutations on the page
```
