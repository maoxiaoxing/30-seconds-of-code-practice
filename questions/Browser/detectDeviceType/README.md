
<a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>

Detects whether the page is being viewed on a mobile device or a desktop.

- Use a regular expression to test the `Navigator.userAgent` property to figure out if the device is a mobile device or a desktop.

```js
const detectDeviceType = () =>
  /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
    navigator.userAgent
  )
    ? 'Mobile'
    : 'Desktop';
```

```js
detectDeviceType(); // 'Mobile' or 'Desktop'
```
