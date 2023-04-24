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

#### 文本标签
定义:为文本添加一些特殊功能
内容:
1. 文本注音,`ruby`标签 包裹注音文字,`rt`标签写拼音  
2. 文本标记,`mark`标签 标注重要内容,显示黄色背景
#### 表单input属性
| 属性名          | 语义                            |
|--------------|-------------------------------|
| placeholder  | 提示文字                          |
| required     | 必填内容,适用于除按钮外的表单控件             |
| autofocus    | 自动获取焦点,适用于所有的表单控件             |
| autocomplete | 自动完成,可以设置为on或off,适用于文字输入类表单控件 |
| pattern      | 输入规则,填入正则表达式,与`required`配合使用  |
#### input类型
| 属性名            | 语义              |
|----------------|-----------------|
| email          | 邮件              |
| url            | 网址              |
| number         | 数字              |
| search         | 搜索              |
| tel            | 电话号码,移动端唤起数字输入框 |
| range          | 范围              |
| color          | 颜色              |
| date           | 日期              |
| month          | 年份 月份           |
| week           | 年份 周数           |
| time           | 时间              |
| datetime-local | 日期 时间           |
| ---表单新增属性---   | ------          |
| novalidate     | 使表单不进行验证        |
#### video标签属性
| 属性名      | 语义                                                |
|----------|---------------------------------------------------|
| width    | 宽度                                                |
| height   | 高度                                                |
| src      | 视频地址                                              |
| controls | 展示视频控件                                            |
| muted    | 静音                                                |
| autoplay | 自动播放                                              |
| loop     | 循环播放                                              |
| poster   | 视频封面                                              |
| preload  | 预加载,可选值`auto,metaplay,none`<br>metaplay指的是预先加载元数据 |
#### audio属性
与video相同
缺少 width,height,poster
#### 全局属性 作用极小 略
#### 解决兼容性问题

-  添加元信息,使浏览器处于最优渲染模式  
`<meta http-equiv="X-UA-Compatible" content="IE=Edge">`
- 优先使用webkit(chromium)内核进行渲染,适用国产浏览器  
`<meta name="renderer" content="webkit">`
- 使用html5shiv.js让低版本浏览器认识h5的语义化标签
```html
<!--[if lt ie 9]>
<script src="路径/html5shiv.js"></script>
<![endif]-->
```