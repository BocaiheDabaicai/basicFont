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

### 主轴对齐方式

属性名:`justify-content`

常用值:

1. `flex-start:主轴起点对齐`(default)

2. `flex-end:主轴终点对齐`

3. `center:居中对齐`

4. `space-between:均匀分布，两端对齐`

5. `space-around:均匀分布，两端距离是中间的一半`

6. `space-evenly:均匀分布，两端距离与中间距离一致`

### 侧轴对齐方式

属性名:`align-items`

常用值:

1. `flex-start:侧轴顶部对齐`

2. `flex-end:侧轴尾部对齐`

3. `center:侧轴中心对齐`

4. `baseline:基线对齐`

5. `stretch:拉伸对齐，前提是子元素未设置侧轴方向上的长度`--------**默认值**

#### 多行对齐

属性名:`align-content`

常用值:

1. `flex-start:侧轴顶部对齐`

2. `flex-end:侧轴尾部对齐`

3. `center:侧轴中心对齐`

4. `space-between:与侧轴两端对齐`

5. `space-around:伸缩项目间的距离相等`

6. `space-evenly:在侧轴上完全平分`

7. `stretch:拉伸对齐，前提是子元素未设置侧轴方向上的长度`--------**默认值**

### 水平垂直居中

1. `单行文字:height=line-height;text-align:center`

2. `背景图片:background-position:center;`

3. `盒模型:`
   
   - `块元素:margin:0 auto;margin-top:(父元素content-子元素盒子高度)/2`
   
   - `行内块、行内元素:text-align:center;父元素设置line-height:height;vertical-align:middle`

4. `定位元素:`
   
   - `未知父元素宽度:left,top,right,bottom设置为0`
   
   - `已知父元素宽度:left,top,right,bottom设置为0;margin:auto`

5. `伸缩盒模型:`
   
   - `方案一:父元素设置:display:flex;justify-content:center;align-items:center`
   
   - `方案二:父元素设置:display:flex;子元素设置margin:auto`

### 基准长度

属性值:`flex-basis:[像素值]`

内容:设置子元素在主轴方向上的长度,默认与子元素大小保持一致
