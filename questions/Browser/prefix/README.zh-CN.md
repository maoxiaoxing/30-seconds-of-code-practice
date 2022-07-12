
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

基于当前浏览器为CSS属性添加前缀。

- 在供应商前缀字符串数组上使用 `Array.prototype.findIndex()` 来测试是否为`Document.body`在它的`CSSStyleDeclaration`对象中定义了一个，否则返回`null`。
- 使用 `String.prototype.charAt()`和`String.prototype.toUpperCase()` 来大写该属性，它将被添加到浏览器供应商前缀字符串中。

```js
const prefix = prop => {
  const capitalizedProp = prop.charAt(0).toUpperCase() + prop.slice(1);
  const prefixes = ['', 'webkit', 'moz', 'ms', 'o'];
  const i = prefixes.findIndex(
    prefix =>
      typeof document.body.style[prefix ? prefix + capitalizedProp : prop] !==
      'undefined'
  );
  return i !== -1 ? (i === 0 ? prop : prefixes[i] + capitalizedProp) : null;
};
```

```js
prefix('appearance');
// 'appearance' on a supported browser, otherwise 'webkitAppearance', 'mozAppearance', 'msAppearance' or 'oAppearance'
```
