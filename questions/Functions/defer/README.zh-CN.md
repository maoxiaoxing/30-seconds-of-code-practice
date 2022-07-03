
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

延迟调用函数，直到清除当前调用堆栈。

- 使用' setTimeout() '，超时时间为' 1 ' ms来添加一个新的事件到事件队列，并允许渲染引擎完成它的工作。
- 使用spread('…')操作符为函数提供任意数量的参数。

```js
const defer = (fn, ...args) => setTimeout(fn, 1, ...args);
```

```js
// Example A:
defer(console.log, 'a'), console.log('b'); // logs 'b' then 'a'

// Example B:
document.querySelector('#someElement').innerHTML = 'Hello';
longRunningFunction();
// Browser will not update the HTML until this has finished
defer(longRunningFunction);
// Browser will update the HTML then run the function
```
