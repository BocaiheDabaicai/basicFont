# 块级格式上下文

内容:

- 元素的一种功能

- 默认关闭，满足某些条件后被开启

开启后的优点:

- 子元素不再产生`margin`塌陷问题

- 本身不会被浮动元素覆盖

- 子元素浮动不会导致本身高度塌陷

开启方式:

1. 根元素,特指`<html>`

2. 浮动元素,`float:left`

3. 绝对定位、相对定位

4. 行内块元素

5. 表格单元格,`display:table`

6. 设置overflow的值，且不为`visible`

7. 伸缩项目,`display:flex`

8. 多列容器,`column-count:1`

9. 设置`column-span`为`all`

10. `display:flow-root`


