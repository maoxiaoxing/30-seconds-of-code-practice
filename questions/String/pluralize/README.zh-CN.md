
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

根据输入的数字返回单词的单数或复数形式，如果提供了字典，则使用可选字典。

- 使用闭包定义一个函数，该函数根据`num`的值将给定的`word`进行复数化。
- 如果`num`是`-1`或`1`，返回单词的单数形式。
- 如果`num`是任何其他数字，返回“复数”形式。
- 省略第三个参数“复数”，使用默认的单数单词+“s”，或在必要时提供一个自定义的复数单词。
- 如果第一个参数是`object`，返回一个函数，该函数可以使用提供的字典解析单词的正确复数形式。

```js
const pluralize = (val, word, plural = word + 's') => {
  const _pluralize = (num, word, plural = word + 's') =>
    [1, -1].includes(Number(num)) ? word : plural;
  if (typeof val === 'object')
    return (num, word) => _pluralize(num, word, val[word]);
  return _pluralize(val, word, plural);
};
```

```js
pluralize(0, 'apple'); // 'apples'
pluralize(1, 'apple'); // 'apple'
pluralize(2, 'apple'); // 'apples'
pluralize(2, 'person', 'people'); // 'people'

const PLURALS = {
  person: 'people',
  radius: 'radii'
};
const autoPluralize = pluralize(PLURALS);
autoPluralize(2, 'person'); // 'people'
```
