# 伸缩盒模型

内容:弹性盒子，控制灵活，兼容性好，移动设备常用。

具体内容:

> **伸缩容器**:开启了flex的元素
> 
> **伸缩项目**:伸缩容器里的子元素，均以块元素进行展示
> 
> 1. 设置伸缩容器,`display:flex`或`display:inline-flex`
> 
> 2. inline-flex很少使用,它的作用是使伸缩容器**横向排开**

### 主轴与侧轴

属性名:`flex-direction`

内容:主轴表示伸缩项目的排列方式，侧轴与主轴垂直

常用值:

1. row

2. row-reverse

3. column

4. column-reverse

### 主轴换行方式

属性名:`flex-wrap`

常用值:

1. nowrap 不换行

2. wrap 自动换行

3. wrap-reverse 反向换行

### 复合写法

`flex-flow:[flex-direction] [flex-wrap] 不推荐，建议分开写`
