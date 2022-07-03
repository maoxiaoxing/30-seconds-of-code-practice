
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

返回已记忆（缓存）的函数。

- 通过实例化新的“Map”对象来创建空缓存。
- 返回一个函数，该函数首先检查该特定输入值的函数输出是否已缓存，如果未缓存，则将其存储并返回，从而将单个参数提供给已记忆的函数。
- 必须使用“function”关键字，以便在必要时更改记忆函数的“this”上下文。
- 允许访问“缓存”，方法是将其设置为返回函数的属性。

```js
const memoize = fn => {
  const cache = new Map();
  const cached = function (val) {
    return cache.has(val)
      ? cache.get(val)
      : cache.set(val, fn.call(this, val)) && cache.get(val);
  };
  cached.cache = cache;
  return cached;
};
```

```js
// See the `anagrams` snippet.
const anagramsCached = memoize(anagrams);
anagramsCached('javascript'); // takes a long time
anagramsCached('javascript'); // returns virtually instantly since it's cached
console.log(anagramsCached.cache); // The cached anagrams map
```
