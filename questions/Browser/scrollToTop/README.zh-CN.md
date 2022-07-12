
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

平滑-滚动到页面顶部。

- 使用`Document.documentElement`或者`Document.body`和`Element.scrollTop`获取到顶部的距离。
- 滚动一小部分的距离从顶部。
- 使用`Window.requestAnimationFrame()`来动画滚动。

```js
const scrollToTop = () => {
  const c = document.documentElement.scrollTop || document.body.scrollTop;
  if (c > 0) {
    window.requestAnimationFrame(scrollToTop);
    window.scrollTo(0, c - c / 8);
  }
};
```

```js
scrollToTop(); // Smooth-scrolls to the top of the page
```
