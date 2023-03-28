### 自己的学习内容
<text style="color:blue">html、html5、css、css3</text>
#### 元素标签
1.标签不必在意显示效果，注重标签含义  
2.块级元素独占一行，可内嵌块级元素、行内元素  
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