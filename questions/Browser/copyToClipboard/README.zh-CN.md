
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

将字符串复制到剪贴板。
仅在用户操作（即在“click”事件侦听器内）的情况下工作。

- 创建一个新的`<textarea>`元素，用提供的数据填充它，并将其添加到HTML文档中。
- 使用`Selection.getRangeAt()`存储所选范围（如果有）。
- 使用`Document.execCommand()`复制到剪贴板。
- 从HTML文档中删除`<textarea>`元素。
- 最后，使用`Selection.addRange()`恢复原始选定范围（如果有）。
- **注意：**您可以使用异步[剪贴板API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API)在大多数当前浏览器中。您可以在[copyToClipboardAsync代码段]（/js/s/copy-to-clipboard-async）中找到更多信息。

```js
const copyToClipboard = str => {
  const el = document.createElement('textarea');
  el.value = str;
  el.setAttribute('readonly', '');
  el.style.position = 'absolute';
  el.style.left = '-9999px';
  document.body.appendChild(el);
  const selected =
    document.getSelection().rangeCount > 0
      ? document.getSelection().getRangeAt(0)
      : false;
  el.select();
  document.execCommand('copy');
  document.body.removeChild(el);
  if (selected) {
    document.getSelection().removeAllRanges();
    document.getSelection().addRange(selected);
  }
};
```

```js
copyToClipboard('Lorem ipsum'); // 'Lorem ipsum' copied to clipboard.
```
