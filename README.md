### 自己的学习内容
<text style="color:blue">html、html5、css、css3</text>
#### 元素标签
1.标签不必在意显示效果，注重标签含义  
2.块级元素独占一行，可内嵌块级元素、行内元素,&lt;p&gt;、&lt;h1&gt;~&lt;h6&gt;、&lt;dt&gt;之间不相互嵌套  
3.行内元素占显示内容的大小，可内嵌行内元素
#### 文本常用标签
<em>1.em</em> 强调  
<strong>2.strong</strong> 强调   
<span>3.span</span> 无预设显示效果  
<cite>4.作品</cite>  
<dfn>5.同上</dfn>     
<del>6.中间划线</del>/<ins>底部划线</ins>  
<code>7.alert(1)</code>  
<samp>8.识别内容</samp>  
<kbd>9.键盘</kbd>  
<abbr title="abcde">10.缩写</abbr>  
<bdo dir="ltr">11.你是爱心的欢喜( ltr / rtl )</bdo>  
<code>12.变量 let <var>a</var> = 1</code>  
<small>13.法律细则</small>  
<b>14.产品评论</b>  
<i>15.用于字体图标、人物说的话</i>  
<u>16.用于标错</u>  
<q>17.引用</q>  
<blockquote>18.块引用,独占一块</blockquote>  
<address>19.地址,独占一块</address>  

#### 绝对路径补充
本地绝对路径  
网络绝对路径
#### 图片格式介绍 
<kbd><var>jpg jpeg</var> 损失细节存储，不支持动态图、透明背景</kbd>  
<kbd><var>png</var> 无损压缩，不支持动态图</kbd>  
<kbd><var>bmp</var> 不进行压缩，保存更多细节，不支持动态图、透明背景 == png+</kbd>  
<kbd><var>gif</var> 显示动态图，显示颜色有限</kbd>  
<kbd><var>webp</var> 显示网页图片，支持动态图，兼容性不足</kbd>  
<kbd><var>base64</var> 显示网页图片，图片本身以编码形式显示</kbd> 
#### 超链接
<blockquote>
<p><em>——属性值</em></p>  
<p>target</p>  
    _self: 在本标签进行跳转</p>
    _blank: 在新标签进行跳转
<p>download</p>
填写下载名或不填
<p><em>——浏览器支持的文件</em></p>
<code>jpg gif mp4 pdf</code><p/>
<code>zip 不可以直接打开</code>
<p><em>——锚点</em></p>
<code>跳转:href="#(锚点名字)"</code><p/>
<code>回到顶部:href="#"</code><p/>
<code>刷新页面:href=""</code><p/>
<code>命名_1:name="(锚点名字)"</code><p/>
<code>命名_2:id="(锚点名字)"<strong> 推荐</strong></code><p/>
<p><em>——唤醒应用</em></p>
<code>打电话:href="tel:电话号码"</code><p/>
<code>发邮件:href="mailto:邮件名"</code><p/>
<code>发短信:href="sms:收件人"</code><p/>
</blockquote>

#### 列表
<em>注意事项</em>  
<ol>
    <li><code>li</code>不建议单独使用</li>
    <li>列表<code>ol、ul、li等等</code>可嵌套其他块内元素、行内元素</li>
</ol>  
<em>类型</em>
<ol>
    <li>ul li 无序列表</li>
    <li>ol li 有序序列表</li>
    <li>dl dt dd 自定义列表<code>dt 为列表头 dd为列表内容</code></li>
</ol>

#### 表格
<em>内容</em>
<ol>
    <li><code>table</code>表格 支持属性：border width height cellspacing</li>
    <li><code>caption</code>表格标题 支持属性：无</li>
    <li><code>thead</code>表格头部 支持属性：height align valign</li>
    <li><code>tbody</code>表格主体 支持属性：height align valign</li>
    <li><code>tfoot</code>表格脚注 支持属性：height align valign</li>
    <li><code>td</code>表格脚注 支持属性：width height align valign rowspan colspan</li>
    <li><code>th</code>表格脚注 支持属性：width height align valign rowspan colspan</li>
</ol>  

<em>注意</em>  
<code>1.td、th的设置会导致整行或整列的宽高改变</code>
#### 常用小标签
<code>1. br 换行</code>  
<code>2. hr 分割,若实现修饰线，后期用css</code>  
<code>3. pre 按原代码显示</code>
#### 表单
<em>form 属性</em>  
<code>1.action: 填入提交地址 </code>  
<code>2.target: 新页签的打开方式 </code>  
<code>3.method: 控制提交方式 </code>  
<code>4.disable: 用在 input textarea select option 上禁用标签 </code>  
<code>5.fieldset legend: 创造信息领域，外部出现边框，legend为标题 </code>  
<em>特别地，使用<code>input</code>输入框需要填入name属性，指定提交数据的名称</em>
#### iframe框架
<em>属性</em>  
<code>1.src 链接地址，单独展示使用</code>  
<code>2.width 宽度</code>  
<code>3.height 长度</code>  
<code>4.frameborder 边框，可选值 0 1</code>  
<code>5.name 边框名，配合target使用</code>  
#### 字符实体
<blockquote>
    <p style="color: red">1.空格 &nbps;</p>
    <p style="color: red">2.小于 &lt;</p>
    <p style="color: red">3.大于 &gt;</p>
    <p style="color: red">4.和 &amp;</p>
    <p>5.引号 &quot;</p>
    <p>6.反引号 &acute;</p>
    <p>7.分 &cent;</p>
    <p>8.镑 &pound;</p>
    <p style="color: red">9.元 &yen;</p>
    <p>10.欧元 &euro;</p>
    <p style="color: red">11.版权 &copy;</p>
    <p>12.注册商标 &reg;</p>
    <p>13.商标 &trade;</p>
    <p style="color: red">14.乘号 &times;</p>
    <p style="color: red">15.除号 &divide;</p>
    <em>更多的字符实体参看：</em><br>
    <a>https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references</a>
</blockquote>

#### 全局属性
<code>1.id 运用在body里，且非&lt;title&gt;标签上</code>  
<code>2.class 主要使用在&lt;div&gt;标签上,接收css样式</code>  
<code>3.style 主要使用在&lt;div&gt;标签上,编写css样式</code>  
<code>4.dir 运用在body里，且非&lt;title&gt;标签上,使用ltr、rtl调整内容的位置</code>  
<code>5.title 主要使用在&lt;div&gt;标签上,使用ltr、rtl调整内容的位置</code>  
<code>6.lang 主要使用在&lt;div&gt;标签上,标注内容的语言</code>
#### meta
<blockquote>
    <p>meta: robot 属性值</p>
    <p>1.index 允许搜索爬虫索引</p>
    <p>2.noindex 不允许搜索爬虫索引</p>
    <p>3.follow 允许搜索爬虫索引,且跟随页面上的链接</p>
    <p>4.nofollow 允许搜索爬虫索引,但不跟随页面上的链接</p>
    <p>5.all 允许索引与跟随</p>
    <p>6.none 不允许索引与跟随</p>
    <p>7.noarchive 不缓存页面内容</p>
    <p>8.nocache 不缓存页面内容</p>
</blockquote>

----

### CSS 层叠样式表
<p>标记语言，用于给HTML设置样式</p>  
<p>1.行内样式（内联样式）:使用在html标签内，由style属性引出</p>  
<p>2.内部样式:推荐使用在head标签内，由标签名引出</p>  
<p>3.外部样式:<span style="color:green">推荐使用</span>，样式写在文件中，由<code>&lt;link rel="stylesheet" href="文件位置" &gt;</code>标签引用(写在head里)</p>  
<strong>样式表优先级</strong>  
<p style="font-size:20px">行内元素>内部样式=外部样式</p>  
<p style="font-size:20px">基础</p>  
<p>1.通配选择器<code>*</code> 选中所有html元素</p>  
<p>2.元素选择器<code>元素标签名</code> 选中某种元素</p>  
<p>3.类选择器<code>.类名</code> 根据class的名称，来选中对应元素</p>  
<u>对于标签来说，要使用多个类名对应的CSS样式，书写如下：</u>
<u>&lt;p class="类名1 类名2" &gt;</u>  
<p>4.id选择器<code>.id名</code> 根据id的名称，来选中对应元素,其余内容同class</p>  
<p>5.交集选择器<code>(标签名.类名)|(.类名1.类名2)</code> 标签名只能有一个，类名可有多个</p>  
<p>6.并集选择器<code>(标签名 , .类名)|(.类名1 , .类名2)</code> 可用标签名、ID名、类名，无数量限制</p>  
<p>7.后代选择器<code>(标签名 后代标签名)</code> 可以使用标签名、ID名、类名，且任意组合，下级标签无数量限制</p>  
<p>8.子代选择器<code>(标签名 > 下一级标签名)</code> 可以使用标签名、ID名、类名，且任意组合</p>  
<p>9.兄弟选择器<code>[相邻兄弟](标签名 + 标签名)//[通用兄弟](标签名 ~ 标签名)</code> 下一个紧邻的选择器//下面所有的选择器</p>  
<p>10.属性选择器<code>(title title= title^= title$= title *=)</code>详见3_css_property.html</p>  
<p>11.伪类选择器，内容较多，详见 4_css_pseudo_class portfolio</p>  
<p>12.选择器优先级，!important>行内样式>ID选择器>类选择器>元素选择器>通配选择器>继承样式</p>  
<code>对于复合的css样式，根据权重确定显示哪种样式</code>  
<code>(x,y,z)<=>(ID选择器,类、伪类、属性选择器,元素、伪元素选择器)</code>  
<code>样式权重高，则优先显示；权重相同，后者覆盖</code>  

### <em>css三大特性</em>
<blockquote>
<p>1.层叠性,样式发生冲突(同样的名称，被设置不同的值)，会根据一定的规则进行覆盖</p>
<p>2.继承性,元素会自动拥有其父元素、其祖先元素上设置的某些样式，优先获得近处的样式</p>
<p>3.优先性,优先级与权重</p>
</blockquote>

### 颜色
<p>1.像素,精细表达网页内容的单位名称</p>  
<p>2.表达方式</p>  
<p>----(1)官方指定名称_mdn_named_color</p>    
<p>----(2)rgb与rgba,rgb调整红绿蓝三种光色,a调整透明性[1不透明、0完全透明]</p>    
<p>----(3)hex与hexa,hex调整红绿蓝三种光色,#0bc3e6 每两位代表一种颜色(十六进制),末尾再添加两位代表透明度</p>    
<p>----(4)hsl与hsla,hsl代表色相度，饱和度，亮度，hsl(x,y,z) 色相盘、百分比、百分比组成，<u style="color:red">很少使用</u></p>    
<p>----(5)Ui设计师提供的设计稿</p>  

### 字体
<blockquote>
<p>1.字体大小,font-size,最小字体与默认字体由浏览器的设置决定</p>
<p>2.字体族,font-family,书写正确的字体名称,可以用逗号隔开多个字体,结尾使用serif||sans-serif(衬线字体||非衬线字体),且不需要加引号</p>
<p>3.字体风格,font-style,主要有normal(默认)、italic(斜体，判别字体斜体是否存在)、oblique(斜体，强制斜体)</p>
<p>4.字体粗细,font-weight,主要有lighter、normal、bold、bolder(少见),可以用数字表示100-400(lighter)、500-600(normal)、700-1000(bold)</p>
<p>5.复合写法,font,(粗细)、(斜体)、大小、字体族</p>
</blockquote>

### 文本
<blockquote>
<p>1.文本颜色，名称、rgb、hex:#xxxxxx、hsl</p>
<p>2.文本间距，letter-spacing|word-spacing,单位px,负值缩小间距</p>
<p>3.文本修饰，text-decoration,可选值 underline、overline、none、line-through,可选线 wavy dotted,且线颜色可以自定义</p>
<p>4.文本缩进，text-indent,一个字体大小值为一个缩进单位 </p>
<p>5.文本对齐，text-align,可选值left(默认)、center、right </p>
<p>6.字体详谈,设置字体大小,因字体设计原因,最终呈现的大小可能与实际大小有偏差;字体出现的位置总是偏下一些 </p>
<p>7.文本行高,line-height,可选值px、normal、数值、百分比,设置时要尽量使行高大于字体大小 </p>
<p>8.行高注意事项: </p>
<p>----(1)行高最小值为0,超过该值则设置为normal</p>
<p>----(2)可以继承到后代元素身上,在父类元素身上使用数值写法最佳</p>
<p>----(3)line-height与height的关系,设置了height,则高度为height;没有设置height,则高度为line-height</p>
<p>9.应用场景: </p>
<p>----(1)多行文字控制行间距</p>
<p>----(2)单行文字设置相对垂直居中,由height=line-height实现</p>
<p>10.文本垂直对齐 <u>(对于单行文字)</u> :顶部无需调整,居中设置height=line-height,底部设置居中设置<code>height=line-height*2-(font-size)-动态调整值</code> </p>
<p>11.垂直属性 vertical-align,常用设定值 top middle baseline bottom,middle指的是与父元素上x字母(假设字母)的中心对齐</p>
</blockquote>

### css列表属性
| 属性名                 | 属性描述   | 属性值                                              |  
|---------------------|--------|--------------------------------------------------|
| list-style-type     | 设置列表符号 | none(常用) square disc(圆形) decimal(数字) alpha roman |
| list-style-position | 设置标签位置 | inside outside(标签在内容外面)                          |
| list-style-image    | 自定义标签  | url("图片位置")                                      |
| list-style          | 复合语句   | type position image                              |
### table表格属性
| 属性名             | 属性描述     | 属性值                                          |  
|-----------------|----------|----------------------------------------------|
| border-width    | 设置边框宽度   | 像素值                                          |
| border-color    | 设置边框颜色   | 颜色值 rgb hex hsl                              |
| border-style    | 设置边框样式   | none dashed solid(实线) dotted(点线) double(双实线) |
| border          | 复合语句     | width color style                            | 
| table-layout    | 控制表格列宽   | fix(固定) auto                                 |
| border-style    | 设置边框样式   | none dashed solid(实线) dotted(点线) double(双实线) |
| border-spacing  | 控制单元格间距  | 单位px , 使用时不能合并单元格                            |
| border-collapse | 合并相邻单元格  | separate collapse                            |
| empty-cells     | 消除空单元格   | show hide  使用时不能合并单元格,同时设置有单元格间距             |
| caption-side    | 设置表格表题位置 | top hide                                     |
<u>border以上的元素(包括border)在其它元素中也可以使用</u>
### background背景属性
| 属性名                 | 属性描述       | 属性值                                             |  
|---------------------|------------|-------------------------------------------------|
| background-color    | 设置背景颜色     | 默认为 transparent(透明色)                            |
| background-image    | 设置背景图片     | url("图片位置")                                     |
| background-repeat   | 设置背景图片重复方式 | repeat no-repeat repeat-x repeat-y              |
| background-position | 设置背景图片的位置  | 水平与垂直两个参数 默认值为center  垂直方向上居中位置为center 可以用像素点表达 |
| background          | 复合表达       | color image repeat position                     |
### cursor鼠标属性
<p>cursor 设置光标样式 pointer(常用)</p>
<p>自定义光标 设置方式: url("光标样式"),pointer</p>

### 常用长度单位属性
| 单位名称       | 单位描述 | 备注                                         |  
|------------|------|--------------------------------------------|
| px         | 像素单位 | 无                                          |
| em         | 大小单位 | 元素大小 = em值 * 字体大小(默认为浏览器的值或父元素的值)          |
| rem        | 大小单位 | 元素大小 = rem值 * 字体大小(从html元素上开始寻找字体值,直到当前元素) |
| %          | 百分比  | 从祖先元素身上寻找值,最终将 值*百分比 给予属性                  |
### 显示模式
| 模式名称         | 模式描述         | 备注                                 |  
|--------------|--------------|------------------------------------|
| block        | 块级元素         | 独占一行 宽度撑满父元素 高度由元素大小决定 可以通过css设置宽高 |
| inline       | 行内元素(内联元素)   | 宽度、高度由内容撑开 无法通过css设置宽高             |
| inline-block | 行内块单位(内联块元素) | 内容与行内元素一致 可以通过css设置宽高              |
### 显示模式总结
<blockquote style="background:rgba(139,218,139,0.21)">
<h3>块元素</h3>
<p>1.主体结构标签:&lt;html&gt; &lt;body&gt;</p>
<p>2.排版标签:&lt;h1&gt;~&lt;h6&gt; &lt;hr&gt; &lt;p&gt; &lt;pre&gt; &lt;div&gt;</p>
<p>3.列表标签:&lt;ul&gt; &lt;ol&gt; &lt;li&gt; &lt;dl&gt; &lt;dt&gt; &lt;dd&<g></g>t;</p>
<p>4.表格标签:&lt;table&gt; &lt;thead&gt; &lt;tbody&gt; &lt;tfoot&gt; &lt;tr&gt; &lt;caption&<g></g>t;</p>
<p>5.其他:&lt;form&gt; &lt;option&gt;</p>
<h3>行内元素</h3>
<p>1.文本标签:&lt;br&gt; &lt;body&gt;</p>
<p>2.其他:&lt;a&gt; &lt;label&gt;</p>
<h3>行内块元素</h3>
<p>1.图片:&lt;img&gt;</p>
<p>2.单元格:&lt;th&gt; &lt;td&gt;</p>
<p>3.表单控件:&lt;input&gt; &lt;textarea&gt; &lt;select&gt; &lt;button&gt;</p>
<p>4.框架标签:&lt;iframe&gt;</p>
<h3>display属性</h3>
<p>支持类型为 block inline-block inline none</p>
</blockquote>