
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

创建对象的深度克隆。

克隆原语、数组和对象，不包括类实例。

- 使用递归。
- 检查传递的对象是否为`null`，如果是，返回`null`。
- 使用`Object.assign()` 和一个空对象(`{}`)来创建原始对象的浅克隆。
- 使用`Object.keys()`和`Array.prototype.forEach()`来确定哪些键值对需要被深度克隆。
- 如果对象是一个 `Array`，设置克隆的长度为原始的长度，并使用`Array.from()`创建一个克隆。

```js
const deepClone = obj => {
  if (obj === null) return null;
  let clone = Object.assign({}, obj);
  Object.keys(clone).forEach(
    key =>
      (clone[key] =
        typeof obj[key] === 'object' ? deepClone(obj[key]) : obj[key])
  );
  if (Array.isArray(obj)) {
    clone.length = obj.length;
    return Array.from(clone);
  }
  return clone;
};
```

```js
const a = { foo: 'bar', obj: { a: 1, b: 2 } };
const b = deepClone(a); // a !== b, a.obj !== b.obj
```
