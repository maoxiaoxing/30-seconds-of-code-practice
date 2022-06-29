
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Binds methods of an object to the object itself, overwriting the existing method.

- Use `Array.prototype.forEach()` to iterate over the given `fns`.
- Return a function for each one, using `Function.prototype.apply()` to apply the given context (`obj`) to `fn`.

```js
const bindAll = (obj, ...fns) =>
  fns.forEach(
    fn => (
      (f = obj[fn]),
      (obj[fn] = function() {
        return f.apply(obj);
      })
    )
  );
```

```js
var view = {
  label: 'docs',
  click: function() {
    console.log('clicked ' + this.label);
  }
};
bindAll(view, 'click');
document.body.addEventListener('click', view.click);
// Log 'clicked docs' when clicked.
```
