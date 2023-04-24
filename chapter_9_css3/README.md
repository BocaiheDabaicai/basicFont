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
1. horizontal
2. vertical
3. both  

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