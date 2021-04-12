# new 操作符

## 创建实例步骤

1. 创建一个空对象 obj ({})
2. 将 obj 的 \_\_proto\_\_属性指向构造函数 constrc 的原型(obj.\_\_proto\_\_ = constrc.prototype)
3. 将构造函数 constrc 内部的 this 绑定到新建的对象 obj, 执行 constrc(类似调用普通函数,只是此时函数的 this 为新创建的对象 obj， obj.constrc())
4. 若构造函数没有返回非原始值(即不是引用类型的值)，则返回该新建对象的 obj(默认会添加 return this),否则返回**引用类型**的值

## 自己实现 new 操作符

```js
function myNew(constrc, ...args) {
    const obj = Object.create(constrc.prototype);

    const result = constrc.apply(obj, args);

    return result instanceof Object ? result : obj;
}

function Foo() {
    this.name;
}

Foo.prototype.user = "swallowJ";

const f = myNew(Foo);
```
