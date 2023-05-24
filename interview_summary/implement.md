### 55. AJAX 原理

简单地说，是异步的`JavaScript` 和`XML`，可以在不重新加载整个网页的情况下，与服务器交换数据，并且更新部分网页。

通过`XmlHttpRequest`对象来向服务器发异步请求，从服务器获得数据，然后用`JavaScript`来操作`DOM`而更新页面

- 创建 `XMLHttpRequest`对象

- 通过 XMLHttpRequest 对象的 `open()` 方法与服务端建立连接

- 构建请求所需的数据内容，并通过`send()`方法发送给服务器端

- 通过 `onreadystatechange `事件监听服务器端的通信状态

- 接受并处理响应的数据结果

- 将处理结果更新到 HTML页面中

### 56. JS 中 this 的情况

1、普通函数调用：this指向全局对象window

2、构造函数调用：this指向新new出的对象

3、对象函数调用：this指向这个对象

4、箭头函数调用：箭头函数里面没有 this ，所以永远是上层作用域this（上下文）

5、apply和call调用：函数体内 this 的指向的是 call/apply 方法第一个参数，若为空默认是指向全局对象window。

6、函数作为数组的一个元素，通过数组下标调用的：this指向这个数组

7、函数作为window内置函数的回调函数调用：this指向window（如setInterval setTimeout 等）

### 57. css预编译处理器

原理:
将最原本的css进行嵌套、设置变量、混入、模块化使用，使得css代码更加简洁、效率高
一共有三种:

1. sass
2. less
3. stylus

### 58. 前端性能优化

1. **减少http请求数**

1）合并图片。当图片较多时，可以合并为一张大图，从而减少http请求数。

2）合并压缩css样式表和js脚本。

一般我们会把css样式表文件放到文件的头部。比如，放到标签中，这样可以让CSS样式表尽早地完成下载。对应js脚本文件，一般我们把他放到页面的尾部。

3）充分利用缓存。

2. **图片优化**

1）尽可能的使用PNG格式的图片，它相对来说体积较小。

2）图片的延迟加载，也叫做懒加载。

3. **使用CDN**

CDN即内容分发网络，可以使用户就近取得所需内容，解决网络拥挤的状况，提高用户访问网站的响应速度。

4. **开启GZIP**

GZIP即数据压缩，用于压缩使用Internet传输的所有文本资源。开启GZIP的方法很简单，到对应的web服务配置文件中设置一下即可。以Apache为例，在配置文件httpd.conf中添加。

5. **构建优化**

使用 Tree-shaking、Scope hoisting、Code-splitting

Tree-shaking是一种在构建过程中清除无用代码的技术。使用Tree-shaking可以减少构建后文件的体积。

### 59. call, apply, bind 三者的区别

- call

改变`this`的指向

第一个参数为`this`的指向对象

可以利用后续参数传参

直接调用

- apply

改变`this`的指向

第一个参数为`this`的指向对象

只存在第二个参数，且类型为数组

直接调用

- bind

改变`this`的指向

第一个参数为`this`的指向对象

可以利用后续参数传参

返回一个函数

### 61. 如何理解 CDN？实现原理？

内容分发网络：就是智能虚拟网络，使用户就近获得所需内容，降低网络拥塞，提高用户访问响应速度和命中率。

CDN 的关键技术主要有内容存储和分发技术。简单来讲，CDN就是根据用户位置分配最近的资源。

应用CDN后，DNS 返回的不再是 IP 地址，而是一个CNAME(Canonical Name ) 别名记录，指向CDN的全局负载均衡。

### 63. 伪元素、伪类区别

**伪类**

指元素的特殊状态

```js
a:link{ 
color: indianred; 
}
```

**伪元素**

指元素的特殊位置

```js
p::before{ 
content: "￥"; 
}
```

### 64. 跨域

说明:浏览器阻止了请求后的数据进行加载渲染，是浏览器对 JavaScript 实施的安全限制

解决方案:

- proxy代理+ Nginx

跨域问题的产生是因为浏览器的同源政策造成的，但是服务器与服务器之间的数据交换是没有这个限制。

通过客户端发送请求给Nginx服务器，Nginx再反向代理给请求的服务器，拿到响应的请求，就返还给客户端

### 65. Event Loop(事件循环) 的执行顺序

- 首先执行同步代码，宏任务

- 同步栈为空，查询是否有异步代码需要执行

- 执行所有微任务

- 执行完，是否需要渲染页面

- 重新开始 Event Loop，执行宏任务中的异步代码

### 67. 浏览器样式兼容

1. 手动重置样式,`*{padding:0,margin:0}`

2. 编写一个reset.css

3. 使用normalize.css

### 60. GC 垃圾回收机制

Javascript 具有自动垃圾回收机制 (GC:Garbage Collecation)，垃圾收集器会定期（周期性）找出那些不在继续使用的变量，然后释放其内存。

### 71. 对比各种继承

**原型链**,`Child.prototype = new Parent()`,继承父属性和方法

优点:

- 子类可以访问父类的属性和方法

缺点:

- 继承不独立，共享父类属性和方法

**借用构造函数**,`Parent.call()`,继承父属性

优点:

- 子类拥有独立的父类属性和方法
- 可以添加参数

缺点:

- 无法实现函数复用
- 无法访问父类的原型对象

**组合继承**,结合*原型链*和*借用构造函数*,最常用

优点:

- 子类拥有父类的属性和方法
- 实现函数复用
- 可以添加参数

缺点:

- 使用两次父类构造方法

**寄生式继承**,与借用构造函数一致

优点:

- 与构造函数类似

缺点:

- 无法实现函数复用

**寄生组合式继承**,调用一次构造函数，最理想

优点:

- 结合 组合继承、寄生继承的优点
- 是目前最优的继承方法

### 72. 什么是原型 ? 什么是原型链 ？

- 原型:指对象的上一级对象

- 原型对象:函数对象上的 prototype 属性的指向

- 原型链: 实例对象上的 __proto__ 属性的指向

- 原型对象的`constructor`:指向下一级对象

- `__prototype__ == [[Prototype]]`
1. 原型链的起点可以是 实例对象、构造函数；终点是`null`
2. 实例对象和其它对象的原型对象是`Object.prototype`
3. 构造函数的原型对象是`Function.prototype`

```js
function create() {
    let Con = [].shift.call(arguments);                // 获取构造函数
    let obj = Object.create(Con.prototype)     // 创建一个对象，并设置该对象的原型
    let result = Con.apply(obj, arguments);            // 绑定 `this` 并执行构造函数
    return result instanceof Object ? result : obj;    // 确保返回值为对象
}
```

### 73. 什么是作用域 ? 什么是作用域链 ?

**作用域**

使变量、函数、对象生效的限定范围，分类上有函数作用域、全局作用域

**作用域链**

这是一种模式，当前作用域不存在指定内容时，会向上一级去查找

### 75. webpack 中 loader 和 plugin 的区别

loader即为文件加载器，操作的是文件，将文件A通过loader转换成文件B，是一个单纯的文件转化过程。

- `loader`:实现文件的转换

plugin即为插件，是一个扩展器，丰富webpack本身，增强功能 ，针对的是在loader结束之后，webpack打包的整个过程，他并不直接操作文件，而是基于事件机制工作，监听webpack打包过程中的某些节点，执行广泛的任务。

- `plugin`:注重点在文件内容上

### 77. 如何自定义一个 webpack 插件 ？

- 声明一个自定义命名的类或函数

- 在原型中新增 apply 方法

- 声明由 Compiler 模块暴露的生命周期函数

- 使用 webpack 提供的 API 或 自行处理内部实例的数据

- 处理完成后，调用 webpack 提供的回调函数

### 81. Map 和 WeakMap 有什么区别？

`object`:

- 对象的键必须是`String`或`Symbol`
- 键值对个数需要手动计算

`Map`:

- 键可以是任意值
- 可以迭代
- 有`size`属性

`WeakMap`:

- 键只能是对象
- 功能和方法上与`Map`一致
- 有垃圾回收机制
- 不能被遍历

### 82. 类数组

`NodeList` 或 `arguments`的JavaScript 对象，有与数组相似的行为，但它们并不共享数组的所有方法。

- 不能直接在类数组对象上调用数组方法

- 可以获取参数

- 可以得到长度

```js
// 扩展运算符
function checkArgs() {
    return [...arguments];
};

// Array.from()
function checkArgs() {
    return Array.from(arguments);
};

// slice()
function checkArgs() {
    return Array.prototype.slice.call(arguments);
};
```

### 83. 防抖和节流

**防抖**

概念: 触发执行函数的定时器，到达时间后执行函数，如果时间内再次触发，则重新计时
原理:`clearTimeout()`清理上一次的定时器

**节流**

概念:一段时间内，限制函数只能触发一次
原理:使用`boolean`类型的数据作标识，定义触发和不触发的规则

### 84. Promise

Promise 对象用于表示一个异步操作的最终完成（或失败）及其结果值，尝试结束后，如果成功则调用 `resolve`，如果出现 `error` 则调用 `reject`

模拟实现:

1. 创建一个 Promise

2. resolve 或 reject 一个 Promise，仅可敲定一次

3. .then() 方法接收回调函数，满足无论 Promise 的状态是否已经敲定，都需要单独处理回调函数
