
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将给定字符串转换为单词数组。

- 使用`String.prototype.split()`和提供的`pattern`(默认为非alpha作为regexp)来转换为字符串数组。
- 使用`Array.prototype.filter()`来删除任何空字符串。
- 省略第二个参数`pattern`来使用默认的regexp。

```js
const words = (str, pattern = /[^a-zA-Z-]+/) =>
  str.split(pattern).filter(Boolean);
```

```js
words('I love javaScript!!'); // ['I', 'love', 'javaScript']
words('python, javaScript & coffee'); // ['python', 'javaScript', 'coffee']
```
