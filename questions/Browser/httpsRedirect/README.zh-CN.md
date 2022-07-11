
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

重定向页面到HTTPS，如果它目前在HTTP。

- 使用 `location.protocol` 获取当前正在使用的协议。
- 如果不是HTTPS，使用`location.replace()`将现有页面替换为HTTPS版本的页面。
- 使用`location.href` 获取完整地址，使用`String.prototype.split()`分割它，并删除URL的协议部分。
- 注意，按下后退按钮不会把它带回到HTTP页面，因为它在历史中被替换了。

```js
const httpsRedirect = () => {
  if (location.protocol !== 'https:')
    location.replace('https://' + location.href.split('//')[1]);
};
```

```js
httpsRedirect();
// If you are on http://mydomain.com, you are redirected to https://mydomain.com
```
