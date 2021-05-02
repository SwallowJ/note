# Babel

[中文文档连接](https://www.babeljs.cn/docs/)

Javascript 编辑器， 代码兼容，源码转换

使用示例

```bash
#将src目录下的代码编译到lib目录
./node_modules/.bin/babel src --out-dir lib

#或者
npx babel src --out-dir lib
```

## 核心库 **@babel/core**

安装

```bash
yarn add @babel/core
```

使用

```js
const babel = require("@babel/core");

babel.transformSync("code", optionsObject);
```

## cli 命令行工具

安装

```bash
yarn add @babel/core @babel/cli
```

```bash
./node_modules/.bin/babel src --out-dir lib
```
