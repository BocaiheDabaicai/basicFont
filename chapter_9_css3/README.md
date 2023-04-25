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