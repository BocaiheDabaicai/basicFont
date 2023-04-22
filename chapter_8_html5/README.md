## html5简介
新一代html标准,广义上说是整个前端
1. 更丰富的javascript接口
2. 更多的语义标签、全局属性
3. 多媒体标签
4. SEO(搜索引擎)友好
5. 移植性好
---
### 语义化标签
| 标签名        | 语义         | 标签闭合 |
|------------|------------|------|
| header     | 头部         | 闭合   |
| footer     | 底部         | 闭合   |
| nav        | 导航         | 闭合   |
| article    | 文章类型       | 闭合   |
| section    | 段落(通常包含标题) | 闭合   |
| aside      | 侧边栏        | 闭合   |
| ~~main~~   | 主要内容,几乎不用  | 闭合   |
| ~~hgroup~~ | w3c标准下被删除  | 闭合   |
> article 可以包含多个 `section`  
> article 内容独立  
> section 主旨内容分成几段
#### 状态标签
meter标签  
定义:已知范围内的标量测量,双标签  
常用属性如下  

| 属性名     | 语义  |
|---------|-----|
| high    | 高度  |
| low     | 低度  |
| max     | 最大度 |
| min     | 最小度 |
| optimum | 最优值 |
| value   | 当前值 |
 > 使用说明:
 > max,min 限定范围  
 > low high optimum 限定红区、黄区、绿区  

progress标签  
定义:进度条
常用属性: max,value
#### 列表标签
datalist标签  
定义:用于搜索框的关键字提示
用法:
1. 内部使用<code>options标签</code>
2. 设置id名
3. 在form表单中,设置list属性,格式:list="id名"  

details标签
定义:常见于展示问题和答案  
用法:
1. 设置<code>details</code>
2. 在details里设置summary作为显示标题,后续内容自行设定