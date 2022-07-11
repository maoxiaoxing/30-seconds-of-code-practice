
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Creates a new `MutationObserver` and runs the provided callback for each mutation on the specified element.

- Use a [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) to observe mutations on the given element.
- Use `Array.prototype.forEach()` to run the callback for each mutation that is observed.
- Omit the third argument, `options`, to use the default [options](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver#MutationObserverInit) (all `true`).

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
