
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

重定向到指定的URL。

- 使用`Window.location.href` 或`Window.location.replace()`重定向到`url`。
- 传递第二个参数来模拟链接点击(`true` -默认)或HTTP重定向(`false`)。

```js
const redirect = (url, asLink = true) =>
  asLink ? (window.location.href = url) : window.location.replace(url);
```

```js
redirect('https://google.com');
```
