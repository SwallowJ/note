# [Promise 概述](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)

## 概念

1. 状态]

-   待定（pending）: 初始状态，既没有被兑现，也没有被拒绝。
-   已兑现（fulfilled）: 意味着操作成功完成。
-   已拒绝（rejected）: 意味着操作失败。

## 使用

1. 基本使用

```ts
new Promise()
    .then((res) => {})
    .catch((err) => {})
    .finally(() => {});
```

2. 组合使用

**Promise.resolve(value)**: 返回一个以给定值的解析偶的 Promise 对象, 如果 value 是一个 Promise,那么将返回这个 Promise

```ts
Promise.resolve("Hello World").then((value) => {
    console.log(value);
});

// Hello World
```

**Promise.reject(value)**: 同 Promise.resolve

**Promise.all**: 等待多个 Promise 全部兑现再进行下一步操作

```ts
Promise.all([p1, p2,...]).then((res) => {
    console.log(res);
});

// [p1.resolve, p2.resolve...]
```

**Promise.race**: 多个 Promise 只要有一个返回则执行接下来的操作

**Promise.allSettled**

**Promise.any**

[promise 实现](mypromise.js)
