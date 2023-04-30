## CSS3

### 私有前缀

`-webkit-(css属性)`  
简介:用于浏览器对新特性的测试,在确认支持之后,前缀就可以去除  

#### 不同浏览器内核的私有前缀如下:

1. Chrome: `-webkit-`

2. Safari: `-webkit-`

3. Firefox: `-moz-`

4. Edge: `-webkit-`

5. ~~Opera~~:`-o-`

6. ~~IE~~: `-ms-`
   
   ### 长度单位
- rem 字体大小倍数单位,与根元素相关

- vw与vh 视野窗口的百分比单位

- vmax与vmin 选择视野窗口最大或最小的边长作为基数长度,单位数字为百分比
  
  ### box-sizing怪异盒模型
  
  两种属性:
1. content-box 默认选项,内容盒模型

2. border-box 怪异盒模型,设置后,宽高表示盒内总和宽高(边框+内边框+内容区)
   
   ### resize
   
   界面端调整盒模型的大小  
   可选值:

3. horizontal

4. vertical

5. both  

表示可以向哪种方向进行放大缩小  
[ 注意事项 ]:需要与overflow配合使用

### 😘box-shadow盒子阴影

内容:为盒子模型添加阴影  
属性:  
`h-shadow v-shadow 水平阴影,垂直阴影`  
`blur 可选,模糊距离`  
`spread 可选,阴影的外延`    
`color 可选,阴影的颜色`  
`inset 可选,阴影内延`  
实例:

```css
 /* 水平位置 垂直位置 模糊程度 外延值 color 内阴值 */
{
    box-shadow: 0 0 10px 10px violet inset  ;
}
```

### opacity 透明度

内容:为整个元素添加透明度,值处于0至1之间.  
[提示]:rgba 类似的颜色背景调整透明度,仅调整颜色的透明度.

### background-origin

内容:设置背景图片的显示位置  
可选值:border-box padding-box(default) content-box

### background-clip

内容:设置图片裁切位置  
可选值:border-box(default) padding-box content-box text(只显示在文字上)  
`text值需要加上私有前缀才可以生效,目前是实验性功能`

### background-size

内容:设置图片大小
可选值:像素值、百分比、预设值(`contain(图片全包含)`,`cover(空间全覆盖)`,`auto(图片真实大小)`)

#### background 复合语句

内容：设置图片

值:`color url repeat position / size origin clip`

> 顺序不唯一
> 
> 但是 position 要在 size 前面

#### background 多背景语句

语句写法:

```css
background:
    复合语句1,
    复合语句2,
    ...,
    复合语句n;
```

#### border-radius 圆角边框

内容:将边框设置为圆角

常用写法:`border-radius:像素值|百分比`

细节写法:

1. `border-top-left:像素值|百分比 (可选值有: top-left top-right bottom-left bottom-right)`

2. `border-top-left:像素值 像素值`(设置椭圆角，分别代表x半径 y半径)

3. `border-radius: 像素值 像素值 像素值 像素值/像素值 像素值 像素值 像素值`（从左上角开始，顺时针转动）

#### outline 外轮廓

内容:在元素边框外侧添加外边框,**不占位**

表达写法:

1. `outline:边框像素值 线类型 颜色`*可以分开写*

2. `outline-offset:像素值`*单独属性，设置与边框的距离*

### text 文本样式

#### 文本阴影

内容:为文字添加阴影

表达值:

```css
/* 水平阴影 垂直阴影 模糊值 颜色 */
text-shadow:h-shadow v-shadow blur color;
```

默认值: `text-shadow:none;`

#### 文本换行

内容:四种形式，使文字的显示形式进行改变

表达值:

```css
/* 可选值有 normal pre pre-wrap pre-line nowrap */
white-space:值;
```

详情介绍:

1. normal 超出边界自动换行

2. pre 原样输出

3. pre-warp 超出父元素边界，进行换行

4. pre-line 前置空格消除，超出父元素边界，进行换行

5. nowrap 不换行

#### 文本溢出

内容:设置文本溢出时的显示形式

表达值:

```css
overflow:hidden;
white-space:nowrap;
text-overflow:clip|ellipsis;
```

属性说明:

`clip 内容溢出进行裁切`

`ellipsis 内容溢出进行缩略，显示...`

#### 文本修饰

内容:将原本的`text-decoration`升级为可拆分的三个属性

1. text-decoration-line

2. text-decoration-style

3. text-decoration-color

#### 文本描边

内容:仅支持webkit内核浏览器

> -webkit-text-stroke-width : 设置描边宽度
> 
> -webkit-text-stroke-color : 设置描边颜色
> 
> -webkit-text-stroke : width color

### 渐变

#### 线性渐变

`background-image:linear-gradient([to 方向值],颜色1 [渐变宽值],颜色2 [],颜色3 [],...)`

示例:

```css
/* 默认方向，从上至下 */
background-image:linear-gradient(red,yellow,green);
/* 改变方向，从左至右 */
background-image:linear-gradient(to right top,red,yellow,green);
/* 设置渐变角度 */
background-image:linear-gradient(0deg,red,yellow,green);
/* 设置渐变宽度 */
background-image:linear-gradient(red 50px,yellow 100px,green 150px);
/* 设置方向，且渐变宽度 */
background-image:linear-gradient(20deg,red 50px,yellow 100px,green 150px);
```

#### 径向渐变

background-image:radial-gradient([像素值 像素值 at 像素值 像素值 ]，颜色1 [像素值]，颜色2，...)

示例:

```css
/* 默认设置，颜色由内到外 */
background-image:radial-gradient(red,yellow,green)  
/* 位置设置，颜色由内到外 */      
background-image:radial-gradient(at left top,red,yellow,green)   
/* 像素设置位置，颜色由内到外 */     
background-image:radial-gradient(at 50px 100px,red,yellow,green);
/* 关键词设置位置，颜色由内到外 */
background-image:radial-gradient(circle,red,yellow,green);
/* 圆的a,b轴设置，颜色由内到外 */
background-image:radial-gradient(100px 100px,red,yellow,green);
/* 默认设置，颜色由像素值进行分布 */
background-image:radial-gradient(red 50px,yellow 100px,green 150px);
/* 综合设置，颜色由像素值进行分布 */
background-image:radial-gradient(100px 50px at 150px 150px,red 50px,yellow 100px,green 150px);
```

#### 重复渐变

在前面两种属性前加上`-repeating-`即可

> 实现机理:使颜色`渐变区块`重复出现在指定内容区中

实例:

```css
width:300px;
height:300px;
border-radius:50%;
background-image:radial-gradient(at 100px 100px,whitesmoke,purple);
border:0;
```

示例图:

![图片](C:\Users\NfryCreator\Desktop\gate\fontLearn\chapter_9_css3\6_css3_simple.png)

### web字体

```css
@font-face{
    font-family:"名称",
    src:url("连接地址") /* 网络地址、本地地址均可 */
}
h1{
    font-family:"对应设置的名称";
}
```

#### 字体图标

```textile
目前提供的是使用阿里的图标库,
介绍了
1. 本地引用
    (1)原生引入
    (2)link引入(最优)
    (3)js引入
2. 在线引入
    (1)src引入
    (2)scrip引入(最简洁)
```

地址在这里:[iconfont-阿里巴巴矢量图标库](https://www.iconfont.cn/ "你会看到很多有趣的图标")

### 2D变换

#### 位移变换

内容:使元素相对于自身发生移动。

使用:`transform:[定位属性]`

定位属性如下：

1. translateX(像素值||百分比)

2. translateY(像素值||百分比)

3. translate(像素值,像素值) `前者左右移动，后者上下移动` 

> 注意点:
> 
> 1. 不脱离文档流
> 
> 2. 定位参考其自身
> 
> 3. 位移比定位使用在浏览器上效率更好
> 
> 4. 可以链式编写
> 
> 5. **对行内元素无效**
> 
> 6. 位移可以配合定位实现块元素居中

### 缩放变换

内容:使元素放大或缩小

使用:`transform:[缩放属性]`

缩放属性:

1. scaleX(像素值||百分比)

2. scaleY(像素值||百分比)

3. scale(像素值,像素值) `前者左右缩放，后者上下缩放`

> 注意点: 
> 
> 1. 对行内元素无效
> 
> 2. 可以使文字小于12px

### 旋转变换

内容:使元素发生旋转

使用:`transform:[旋转属性]`

旋转属性:

1. rotateX(角度值)    绕着X轴旋转

2. rotateY(角度值)    绕着Y轴旋转

3. rotateZ(角度值)    绕着Z轴旋转  等价于 rotate(角度值)

### 扭曲变换(了解)

内容:使元素发生**旋转拉长**

使用:

1. `transform: skewX(角度值)`

2. `transform: skewY(角度值)`

3. `transform: skew(角度值,[角度值])`

### 多重变换

内容:组合使用2D属性

方式:

`transform:translate() scale() rotate()`

> 注意: rotate最好放在最后，保证位移的准确，否则X轴和Y轴会发生变化。

### 原点变换

内容:对旋转、缩放原点进行改变

方式:

`transform-origin:(关键词、像素值、百分比) [可选值二]`

> 注意点:
> 
> 1. 默认原点X、Y轴居中
> 
> 2. 对位移无效