
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

平滑地滚动调用它的元素到浏览器窗口的可见区域。

- 使用``Element.scrollIntoView()` `滚动元素。
- 使用`{ behavior: 'smooth' }` 平滑滚动。

```js
const smoothScroll = element =>
  document.querySelector(element).scrollIntoView({
    behavior: 'smooth'
  });
```

```js
smoothScroll('#fooBar'); // scrolls smoothly to the element with the id fooBar
smoothScroll('.fooBar');
// scrolls smoothly to the first element with a class of fooBar
```
