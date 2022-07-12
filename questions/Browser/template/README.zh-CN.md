
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

向元素添加事件监听器，并能够使用事件委托。

- 使用`EventTarget.addEventListener()`为元素添加事件监听器。
- 如果有一个target属性提供给选项对象，确保事件目标匹配指定的目标，然后通过提供正确的`this`上下文调用回调。
- 省略`opts`默认为非委托行为和事件冒泡。
- 返回一个自定义委托函数的引用，以便可以与[`off`](/js/s/off)一起使用。

```js
const on = (el, evt, fn, opts = {}) => {
  const delegatorFn = e =>
    e.target.matches(opts.target) && fn.call(e.target, e);
  el.addEventListener(
    evt,
    opts.target ? delegatorFn : fn,
    opts.options || false
  );
  if (opts.target) return delegatorFn;
};
```

```js
const fn = () => console.log('!');
on(document.body, 'click', fn); // logs '!' upon clicking the body
on(document.body, 'click', fn, { target: 'p' });
// logs '!' upon clicking a `p` element child of the body
on(document.body, 'click', fn, { options: true });
// use capturing instead of bubbling
```
