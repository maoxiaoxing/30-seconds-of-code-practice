
<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>

延迟异步函数的执行。

- 延迟' async '函数的部分执行，将其置于睡眠状态，并返回一个' Promise '。

```js
const sleep = ms => new Promise(resolve => setTimeout(resolve, ms));
```

```js
async function sleepyWork() {
  console.log("I'm going to sleep for 1 second.");
  await sleep(1000);
  console.log('I woke up after 1 second.');
}
```
