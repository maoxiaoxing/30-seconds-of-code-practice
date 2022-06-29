
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将对象的方法绑定到对象本身，覆盖现有的方法。

-使用' Array.prototype.forEach() '迭代给定的' fns '。
-为每个对象返回一个函数，使用' function .prototype.apply() '将给定的上下文(' obj ')应用到' fn '。

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
