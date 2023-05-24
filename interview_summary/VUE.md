### 1. 介绍一下 MVVM 模式，和 MVC 模式有什么区别？

**MVVM**

三个组成部分modal（数据模型）、view（视图）、viewModal（视图模型）

1. 视图将页面通过视图模型转换为数据模型上的数据，通过DOM事件监听实现

2. 数据模型上的数据通过视图模型转换为页面，通过数据绑定实现

当两端的数据同步变更的时候，实现双向绑定

**MVC**

三个部分组成view、modal、Controller（控制器）

1. 数据模型可以访问视图

2. 视图必须通过控制器访问模型

> 总结:
> 
> - MVVM实现双向通信
> 
> - MVC实现单向通信

### 2. Vue 的生命周期有哪些

**vue2的生命周期**

初始化阶段的钩子函数：

```js
beforeCreate()//实例创建前：模板和数据均未获取到
created()//实例创建后：最早可以获得data数据，但模板还未获取到
beforfeMount()//数据挂载前：模板已经获取到，但是数据未挂载到模板上
mounted()//数据挂载后：数据已挂载到模板中
```

更新阶段的钩子函数：

```js
beforeUpdate()//模板更新前：data改变后，更新数据模板前调用
updated()//模板更新后：将data渲染到数据模板中
```

销毁阶段的钩子函数：

```js
beforeDestroy()//实例销毁前
destroyed()//实例销毁后
```

**vue3的生命周期**

初始化阶段的钩子函数：

```js
setup()//实例创建后：获得data数据，但模板还未获取到
beforfeMount()//数据挂载前：模板已经获取到，但是数据未挂载到模板上
mounted()//数据挂载后：数据已挂载到模板中
```

更新阶段的钩子函数：

```js
beforeUpdate()//模板更新前：data改变后，更新数据模板前调用
updated()//模板更新后：将data渲染到数据模板中
```

销毁阶段的钩子函数：

```js
beforeUnmount()//实例卸载前
unmounted()//实例卸载后
```

### 3. keep-alive

`keep-alive`: 是一个内置组件，它的功能是在多个组件间动态切换时缓存被移除的组件实例

```js
//被激活的组件可以使用两个生命周期钩子，activated,deactivated
// 组件被激活时触发
activated(){

}
// 组件失活时触发
deactivated(){

}
```

### 4. 父子组件生命周期执行顺序

**挂载阶段**

1. 父组件先执行`beforeCreate()`,`created()`,`beforeMounted()`

2. 子组件再执行`beforeCreate()`,`created()`,`beforeMounted()`,`mounted()`

3. 最后父组件执行`mounted()`

**更新阶段**

1. 父组件先执行`beforeUpdate()`

2. 子组件再执行`beforeUpdate()`,`updated()`

3. 最后父组件执行`updated()`

**销毁阶段**

1. 父组件先执行`beforeDestroy()`

2. 子组件再执行`beforeDestroy()`,`destroyed()`

3. 最后父组件执行`destroyed()`

### 5. 平时发送异步请求在哪个生命周期，并解释原因

- 三个钩子函数 created、beforeMount、mounted 可以进行异步请求，因为data 已经创建，可以将服务端端返回的数据进行赋值。

- 推荐在 created 钩子函数中调用异步请求，因为此时没有拿到模板，可以更好地处理数据；

- SSR 不支持 beforeMount 、mounted 钩子函数，放在 created 中有助于一致性。

**created 和 mouted 区别**

区别主要在于`created`没有模板，不可以操作DOM元素

所以，

1. created 钩子函数适用于组件初始化时使用

2. mounted 钩子函数适用于需要操作组件的 DOM 元素时使用

### 6. 组件中的 data 为什么是一个函数？

我们可以先假设data既可以是对象也可以是函数

1. 对象写法

如果data是一个对象，在创建组件实例对象后，多个对象是共用原型对象上的属性和方法的

会导致数据不独立的问题产生

```js
function Component() {}
Component.prototype.data = {
  count: 1,
};

// 创建两个组件实例
const componentA = new Component();
const componentB = new Component();

// 当修改其中一个组件的中的data值的时候，另一个组件的data值会一起改变
componentA.data.count = 2;
console.log(componentB.data.count); // 2
```

2. 函数写法

通过函数返回给data一个对象，这个对象是独立的，那么对象之间使用相同内容的属性不会相互干扰

```js
function Component() {
  this.data = this.data();
}
Component.prototype.data = function () {
  return {
    count: 1,
  };
};

// 创建两个组件实例
const componentA = new Component();
const componentB = new Component();

// 当修改其中一个组件的中的data值的时候，另一个组件的data值不会一起改变
componentA.data.count = 2;
console.log(componentB.data.count); // 1
```

因此data以函数的形式存在

### 7. v-model 是什么，有什么用？

`v-model`是一个常用的表单指令，也是唯一一个双向绑定指令。双向的含义是：状态的变化能更新到视图上；用户在表单中的修改也能更新到状态中。

### 8. Vue 的双向数据绑定是如何实现的

**实现:**

1. 采用数据劫持结合发布者-订阅者模式的方式，

2. 通过 Object.defineProperty() 来给各个属性添加 setter，getter 方法并劫持监听，

3. 在数据变动时发布消息给订阅者，触发相应的监听回调

**个人认为**

**视图端**

1. 监听视图上的数据变化

2. 发生变化后，由`Object.defineProperty()`上的getter，setter方法对数据模型上的数据进行更新

3. 使视图和数据模型上的数据保持同步

**数据模型端**

1. 监听数据模型上的数据变化

2. 发生变化后，由`Object.defineProperty()`上的getter，setter方法对视图上的数据进行更新

3. 使视图和数据模型上的数据保持同步

就必须要实现以下几点：

1、实现一个数据监听器 Observer，能够对数据对象的所有属性进行监听，如有变动可拿到最新值并通知订阅者。

2、实现一个指令解析器 Compile，对每个元素节点的指令进行扫描和解析，根据指令模板替换数据，以及绑定相应的更新函数。

3、实现一个 Watcher，作为连接 Observer 和 Compile 的桥梁，能够订阅并收到每个属性变动的通知，执行指令绑定的相应回调函数，从而更新视图。

### 9. 为什么 Vue3 用 proxy 代替了 Vue2 中的 Object.defineProperty

`Object.defineProperty`的不足:

1. Object.defineProperty 不能监控数组下标的变化，导致通过数组下标添加的元素不能实时响应

2. Object.defineProperty 只能监听对象的属性，导致需要对每个对象、每个属性都进行遍历，如果属性值也是对象，则需要进行深度遍历。

`proxy`:

1. 对整个对象进行代理，所以可以监听对象某个属性值的变化

2. 可以监听对象属性的新增和删除，而且还可以监听数组

### 10. this.$set() 的用处及用法

由于 Vue2 中的 Object.defineProperty 在实现数据监听上有一些缺陷，`this.$set()` 就是为了解决这一缺陷而产生的。

当我们想让一个数据的变化变为响应式时，可以使用 `this.$set()` 向响应式对象中添加一个属性，来确保这个新属性同样是响应式的，且触发视图更新。

它必须用于向响应式对象上添加新属性，因为 Vue 无法探测普通的新增属性。

### 11. Vue 中的数据为什么频繁变化时只会更新一次

Vue异步执行DOM更新。

只要观察到数据变化，Vue将开启一个队列，并缓冲在同一事件循环中发生的所有数据改变。

如果同一个watcher被多次触发，只会被推入到队列中一次。

nextTick 方法会在队列中加入一个回调函数，确保该函数在前面的 Dom 操作完成后才调用。

### 12. this.$nextTick() 作用及实现原理

this.$nextTick() 就是等待数据的作用，将一些回调延迟，等到 DOM 更新之后再开始执行。

nextTick 主要使用了宏任务和微任务

根据执行环境分别尝试采用 Promise、MutationObserver、setImmediate 如果以上都不行则采用 setTimeout。
