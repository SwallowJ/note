# [WebAssembly](https://www.wasm.com.cn/getting-started/js-api/)

## 加载

### 1. 获取.wasm 二进制文件， 将它转换成类型数组或者 ArrayBuffer

-   网络, XHR, fetch, 文件获取, indexDB, 直接在 js 合成

### 2. 将二进制数据编译成一个 WebAssembly.Module

方法 WebAssembly.compile

### 3. 使用 imports 实例化这个 WebAssembly.Module, 获取 exports
