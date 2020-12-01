#### 高频面试题（笔试题）

1、简述 <!doctype> 的作用？

+ 声明文档类型，告诉浏览器以哪种规范来解析文档

2、常见的浏览器及其内核？ 

+ 浏览器：IE，Chrome，FireFox，Safari，Opera。

  内核：Trident，Gecko，Presto，Webkit。

  使用Trident的是internet explorer，国产的绝大部分浏览器。Trident是就是ie内核

  使用Gecko的是Mozilla Firefox，使用 Gecko 内核的浏览器也有不少，如 Netscape MozillaSuite/SeaMonkey 等

  使用Presto的是opera，这是目前公认网页浏览速度最快的浏览器内核

  使用WebKit的有苹果的safari，谷歌的chrome，还有国产的大部分双核浏览器其中一核就是WebKit

3、b 和 strong（i 和 em）标签的区别？ 

这是第二次修改

+ b标签是一个实体标签，它所包围的字符被设为bold（粗体)，而strong标签是一个语义标签，作用是加强字符的语义

  em标签告诉浏览器把其中的文本表示为强调的内容。对于所有浏览器来说，这意味着要把这段文字用斜体来显示。

4、谈谈对语义化的理解？

+ 运用合适的标签和特定的属性去格式化文档，简单讲就是根据内容的结构化（内容语义化），选择合适的标签（代码语义化）便于开发者阅读和写出更优雅的代码的同时让浏览器的爬虫和机器很好地解析，有利于SEO，便于团队开发和维护。

5、CSS 引入方式有哪些？ 

+ （1）内嵌式

  通过<style\></style\>来书写CSS代码。

  只能应用于当前网页，不能被其它网页共享。

  注意：<style\>标记可以放在网页的任何地方，但一般放在<head>。

  （2）外联式

  通过<link\>标记来引入外部的CSS文件(.css)。

  可以被其它网页共享。

  格式：<link href="CSS的URL" rel="stylesheet" type="text/css" />

  注意：<link\>标记只能放在<head>中

  （3）行内样式

  通过style的属性来书写CSS代码。

  举例：<p style=“font-size:24px;” \></p\>

6、CSS 基本选择器有哪些？ 

+ a.内联样式表的权值为1000

  b.ID选择器的权值为100

  c.class类选择器的权值为10

  d.HTML标签选择器的权值为1
  
  e.通配符选择器

7、如何合并表格单元格？ 

+ table合并单元格 colspan（跨列）和rowspan（跨行）

8、thead、tbody、tfoot 有什么用？

+ thead　表格的头 用来放标题之类的东西

  tbody　表格的身体 放数据本体 

  tfoot　 表格的脚 放表格的脚注之类

9、常见表单元素有哪些？ 

+ 1.input :标签用于搜集用户信息。

  2.textarea标签定义多行的文本输入控件。

  3.button:定义一个按钮。

  4.select:定义一个选择列表，即下拉列表。 option:定义下拉列表中的选项。

10、请简述一下盒模型的组成？ 

+ 什么是盒模型：盒模型又称框模型（Box Model）,包含了元素内容（content）、内边距（padding）、边框（border）、外边距（margin）几个要素。

+ 元素框的总宽度 = 元素（element）的width + padding的左边距和右边距的值 + margin的左边距和右边距的值 + border的左右宽度；

  元素框的总高度 = 元素（element）的height + padding的上下边距的值 + margin的上下边距的值 ＋ border的上下宽度。

11、CSS 复合选择器有哪些？

+ 群组选择器、交集选择器、子代选择器、后代选择器

12、块级标签和行内标签的区别？ 

+ Html中常见行级标签：span、a、em、strong、b ......

  特点：在一行内显示（在一行中可以并列多个行级标签），不能设置宽高属性，只有水平内外边距可以生效

  Html中常见块级标签：div、p、ul、li、dl、td、dd、h1~h6 ......

  特点：独占一行，能设置width，height属性，水平垂直内外边距都生效

13、浮动产生的问题？清除浮动的方案？ 

+ （1）给父级元素加高度（不推荐使用，它只适合高度固定的布局，一般父盒子都是为由内容撑起来）

  （2）在结尾处添加空div标签clear:both。具体做法：添加一个div标签并定义一个cl的类名，给cl类名添加样式clear:both，将该div标签放到父元素内容结束前的位置（缺点：会多加CSS和HTML标签）。

  （3）给父级元素定义 overflow:hidden（推荐使用，缺点：不能和position配合使用，因为超出的尺寸的会被隐藏）

  （4）给父级div定义伪类：after（推荐使用）

  ```css
  clearfloat:after
  {display:block;clear:both;content:"";}
  ```

14、伪元素如何创建 ?

+ div::after  div::before

15、如何实现盒子水平垂直居中？

+ 方案1、margin 负间距

  1.必需知道该div的宽度和高度，

  2.然后设置位置为绝对位置，

  3.距离页面窗口左边框和上边框的距离设置为50%，这个50%就是指盒子左上角顶点距离页面左、上边界的50%，

  4.最后将该div分别左移和上移，使整个盒子居中，左移和上移的大小就是该DIV(包括border和padding)宽度和高度的一半。

  ```
  <!DOCTYPE html>
  <html>
  <head>
  	<title>my-test</title>
  	<style type="text/css">
  		* {
  			margin: 0;
  			padding: 0;
  		}
  		.content {
  			
  			position: absolute;
  			width: 200px;
  			height: 200px;
  			border: 2px solid red;
  			background-color: yellow;
  			left:50%;
  			top:50%;
  			margin-left:-102px;
  			margin-top:-102px;
  		}
   
  	</style>
  </head>
  <body>
  	<div class="content">
  		我有固定的宽度和高度。
  	</div>
  </body>
  </html>
  ```

  方案2、margin:auto实现绝对定位元素的居中（该方法兼容ie8以上浏览器）

  此方案代码关键点：

  1、上下左右均0位置定位；

  2、margin: auto;

  ```
  <!DOCTYPE html>
  <html>
  <head>
  	<title>my-test</title>
  	<style type="text/css">
  		* {
  			margin: 0;
  			padding: 0;
  		}
  		.content {
  			
  			position: absolute;
  			width: 200px;
  			height: 200px;
  			border: 2px solid red;
  			background-color: yellow;
   
  			left: 0;
  			right: 0;
  			top: 0;
  			bottom: 0;
  			margin: auto;
  		}
   
  	</style>
  </head>
  <body>
  	<div class="content">
  		我有固定的宽度和高度。
  	</div>
  </body>
  </html>
  ```

16、图片下方空白间隙如何解决？ 

+ 两个图片之间和图片下方多出的空白间隙可以使用以下方式解决。

  方法 1：将图片显示为块：解决下方间隙

  ```
  img{
  display:block;
  }                
  ```

  方法 2：改变图片的 vertical-align :解决下方间隙

  ```
  img{
  vertical-align:middle; 
  }    
  ```

  除了 middle值，还可以设置为 top| bottom 等

  方法 3：设置图片父级标签的 font-size:0;line-height:0; 水平间隙，图片下方间隙都能解决

  ```
  .imgwrap{
  font-size:0;
  line-height:0;
  }     
  ```

17、请简述 等高布局、圣杯布局、双飞翼布局的实现原理。

+ **等高布局**

  方法一、利用内外边距相抵消，注意父元素设置 "overflow:hidden;"

  方法二、原理：利用内容撑开父元素的特点，给每一列添加相对应用的容器，并进行相互嵌套，并在每个容器中设置背景色。（这里需要提醒大家你有多少列就需要多少个容器，比如说我们说的三列，那么你就需要使用三个容器）

  **圣杯布局：**

  圣杯布局和双飞翼布局都是为了实现左右两栏固定宽度，中间部分自适应的三栏布局，不过两者实现的原理有所不同。以下是圣杯布局实现思路。

  1. 将三者都 float:left , 再加上一个position:relative (因为相对定位后面会用到）
  2. middle部分 width:100%占满
  3. 此时middle占满了，所以要把left拉到最左边，使用margin-left:-100%
  4. 这时left拉回来了，但会覆盖middle内容的左端，要把middle内容拉出来，所以在外围container加上 padding:0 220px 0 200px
  5. middle内容拉回来了，但left也跟着过来了，所以要还原，就对left使用相对定位 left:-200px  同理，right也要相对定位还原 right:-220px
  6. 到这里大概就自适应好了。如果想container高度保持一致可以给left middle right都加上min-height:130px

  **双飞翼布局**

  双飞翼布局，始于淘宝UED。如果把三栏布局比作一只鸟，可以把main看成是鸟的身体，left和right则是鸟的翅膀。这个布局的实现思路是，先把最重要的身体部分放好，然后再将翅膀移动到适当的地方.

  左翼left设置200px,右翼right设置220px身体main自适应

  1. html代码中，main要放最前边，然后是left  right
  2. 将main  left  right 都float:left
  3. 将main占满 width:100%
  4. 此时main占满了，所以要把left拉到最左边，使用margin-left:-100%  同理 right使用margin-left:-220px
  5. main内容被覆盖了吧，除了使用外围的padding，还可以考虑使用margin。给main增加一个内层div-- main-inner, 然后margin:0 220px 0 200px
  6. main正确展示

18、简述 CSS 精灵图原理，及优缺点？ 

+ 英文叫法 css sprites，通常被解释为“CSS 图像拼合”或“CSS 贴图定位”；其实就
  是把网页中一些背景图片整合到一张图片文件中，再利用 CSS “background-image”，
  “background- repeat”，“background-position”的组合进行背景定位，background-position 用数字能精确的定位出背景图片的位置。适用于一般小图标，不适合大背景大布局背景

  优点：

  （1）减少网页的 http 请求，从而大大的提高页面的性能

  （2）图片命名上的困扰

  （3）更换风格方便

  缺点：

  （1）必须要限定容器大小符合背景图元素位置，需要计算

19、简述 BFC 规则及解决的问题？ 

+ Block Formatting Context (块级格式化上下文)
+ 它是指一个独立的块级渲染区域，只有Block-level BOX参与， 该区域拥有一套渲染规则来约束块级盒子的布局，且与区域外部无关。
+ 怎样生成**BFC**
  - 根标签
  - float的值不为none
  - overflow 的值不为 visible 
  - display 的值为 inline-block
  - position 的值为 absolute 或 fixed
+ **BFC**的特性
  - 内部的标签默认会在垂直方向上一个接一个的放置。
  - 垂直方向上的距离由margin决定，属于同一个BFC的两个相邻标签的margin会发 生重叠。
  - 每个标签的左外边距与包含块的左边界相接触（从左向右），即使浮动标签也是如此。
  - 计算BFC的髙度时，浮动子标签也参与计算。
  - BFC就是页面上的一个隔离的独立容器，容器里面的子标签不会影响到外面标签， 反之亦然。
+ **BFC**解决的问题
  - 外边距塌陷
  - 清浮动

20、文本溢出显示省略号如何实现？

+ （1）单行文本溢出显示省略号

  ```
  P{
      width:200px； /*限定盒子的宽度*/
      overflow:hidden;   /*给元素设置溢出隐藏属性*/
      text-overflow:ellipsis;  /*文本溢出显示省略号*/
      white-space:nowrap; /*文本不换行*/
  }
  ```

  （2）多行文本溢出显示省略号

  方法1：利用WebKit的CSS扩展属性(只有-webkit内核才有作用)

  ```
  P{
  	width:200px； /*限定盒子的宽度*/
  	overflow: hidden; /*给元素设置溢出隐藏属性*/
      text-overflow: ellipsis; /*文本溢出显示省略号*/
      display: -webkit-box; /*将对象作为弹性伸缩盒子模型显示*/
     -webkit-line-clamp: 2;/*用来限制在一个块元素显示的文本的行数,这是一个不规范的属性，它没有出现在 CSS 规范草案中。*/
     -webkit-box-orient: vertical;/*设置或检索伸缩盒对象的子元素的排列方式*/
  }
  ```

  方法2：利用伪元素模拟溢出显示省略号的效果（兼容性比较好）

  实现要点：

  将height设置为line-height的整数倍，防止超出的文字露出。

  给 .p1:after 添加渐变背景可避免文字只显示一半。


21、为什么要初始化 CSS 样式？哪些样式需要初始化？ 

+ 因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。

  ```
  body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }
  body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }
  h1, h2, h3, h4, h5, h6{ font-size:100%; }
  address, cite, dfn, em, var { font-style:normal; }
  code, kbd, pre, samp { font-family:couriernew, courier, monospace; }
  small{ font-size:12px; }
  ul, ol { list-style:none; }
  a { text-decoration:none; }
  a:hover { text-decoration:underline; }
  sup { vertical-align:text-top; }
  sub{ vertical-align:text-bottom; }
  legend { color:#000; }
  fieldset, img { border:0; }
  button, input, select, textarea { font-size:100%; }
  table { border-collapse:collapse; border-spacing:0; }
  ```

22、display:none 和 visibity：hidden 的区别？ 

+ display:none：隐藏该元素并且该元素所占的空间也不存在了

  visibility:hidden ：隐藏该元素但是该元素所占的内存空间还存在，即“隐身”效果

23、你能想出几种方法让元素在页面中消失？ 

+ 1.display:none;（将整个元素隐藏，并且不会占据任何的空间） 

  2.visibility:hidden;（元素的内容不可见，但是元素仍然保持原来的位置和大小）

  3.设定它的位置,让其消失不见：

  position:absolute或fixed，用z-index遮盖。

  4.overflow:hidden将要隐藏的元素移除父元素的范围。

  5.设置元素为透明：即opacity:0；

  6.设置元素的clip（在新的css中使用clip-path来代替clip） 
  要让其生效，必须给元素的position的值设置为absolute或者fixed。

  7.将元素的font-size，line-height,width,height设置为0；（虽然这些方法很赖皮。）

  8.设置元素的transform的translateX（Y）的值为-100%；

24、标签应该如何合理嵌套？ 

+ ul,li/ol,li/dl,dt,dd拥有父子级关系的标签；ul、ol下都只能跟li，dl下只能跟dt.dd。

  p,h标签里面不能嵌套块元素；

  a标签不能嵌套a；

  行内元素不能嵌套块元素；

25、简述网页中常见图片格式及特点？

+ | 格式 | 优点                                       | 缺点                               | 使用场景                   |
  | ---- | ------------------------------------------ | ---------------------------------- | -------------------------- |
  | jpg  | 色彩丰富，文件小                           | 有损压缩，反复保存图片质量下降明显 | 色彩丰富的图片/渐变图像    |
  | gif  | 文件小，支持动画、透明，兼容性比较好       | 只支持256种颜色                    | 色彩简单的logo/icon/动图   |
  | png  | 无损压缩，支持透明，简单图片尺寸小         | 不支持动画，色彩丰富的图片尺寸大   | logo/icon/透明图           |
  | webp | 文件小，支持有损和无损压缩，支持动画、透明 | 浏览器兼容性不好                   | 支持webp格式的app和webview |

26、说说你了解的浏览器兼容问题有哪些？ 

+ ie8中图片边框问题

  Ie8 中图片放在a标签中显示边框。

  解决方案:

  ```
   img{
  border:none;
  }
  ```

  ie8中背景复合属性写法问题

  如下代码，在标准浏览器中均能正常显示背景图片，但是在ie8中图片显示异常。

  ```
  .bg{ 
  background:url(“./images/bg.jpg”)no-repeat center;
  }
  ```

  解决方案:在url和no-repeat之间加上空格

  ```
  .bg{ 
  background:url(“./images/bg.jpg”) no-repeat center;
  }
  ```

  其他ie低版本兼容性问题了解

  1.在 IE6 及更早浏览器中定义小高度的容器？

  解决方案：

  ```
  #test{
  overflow:hidden;
  height:1px;
  font-size:0;
  line-height:0;
  }
  ```

  2.IE6 及更早浏览器浮动时产生双倍边距的 BUG ？

  解决方案：针对 ie6 设置该标签的 display 属性为 inline 即可

  ```
  #test{
  float:left;
  _display:inline;
  }  
  ```

  3.IE7 及更早浏览器下子标签相对定位时父标签 overflow 属性的 auto|hidden 失效的问题

  解决方案：给父标签也设置相对定位 position:relative;

  块转内联块 ie7- 不在一行显示问题

  解决方案：

  ```
  div {
   display:inline-block;
  *display:inline;
  *zoom:1;
  }
  ```

27、什么是 CSSHack 技术？

+ 不同的浏览器对CSS的解析结果是不同的，因此会导致相同的CSS输出的页面效果不同，这就需要CSS Hack来解决浏览器局部的兼容性问题。而这个针对不同的浏览器写不同的CSS 代码的过程，就叫CSS Hack。
+ CSS属性Hack、CSS选择符Hack以及IE条件注释Hack

28、在项目中你是如何做图片优化的？

+ 使用背景图 
  - 对于页面中与页面内容无关，起修饰作用的图片，使用背景图 background-image（如页面中小图标尤其多次重复出现的，纹理性的背景），与页面内容相关展示性的图片如（广告图、产品图）使用 img 标签。 
+ 图片品质  
  - 注意图片优化：在保证视觉效果的情况下，选择最小的图片格式与图片质量，以减少加载时间。
  - 注：通常颜色丰富线条复杂的图片选择 .jpg，颜色单一的小图片使用 .gif，需要更好的显示细节或需要支持半透明的图片使用 .png 等。
+ 使用精灵图 
  - 运用 CSS sprites 技术集中小的背景图或图标，减少页面 http 请求。

29、html5 有哪些新特性？ 

+ 用于绘画的 canvas 元素

  用于媒体的 video 和 audio 元素

  新的特殊内容元素，比如 article、footer、header、nav、section

  新的表单控件，比如 calendar、date、time、email、url、search

30、如何处理 HTML5 新标签的浏览器兼容问题？

+ HTML5新标签对IE低版本浏览器的影响及兼容情况处理方案：

  ```
  方案一：使用javascript新增元素的方法解决
  document.createElement(“header”);
  document.createElement(“footer”);
  …
  ```

  由于创建出来的元素是内联元素，所以需要转换成块级，宽度和高度才能生效。

  ```
  header,footer{ display:block;}
  ```

  方案二：使用封装好的插件html5shiv.js解决兼容性问题。

  ```
  <!--[if lt IE 9]>
  <script type="text/javascript"  src="./html5shiv.js"></script>
  <![endif]-->
  ```

  上面这段代码仅会在IE浏览器下运行。

31、CSS3 有哪些新特性？ 

+ 选择器
+ 背景和边框阴影
+ 文本效果
+ 2D/3D 转换
+ 动画
+ 多列布局

32、CSS3 新增选择器有哪些？

+ **属性选择器**

  属性选择器在CSS2中就被引入，即E[attr]、E[attr=”value”]、E[attr~=”value”]。

  **结构性伪类选择器**

  :first-child 选择器：用于选取属于其父元素的首个子元素的指定选择器

  :last-child 选择器：匹配属于其父元素的最后一个子元素的每个元素

  :nth-child() 选择器：匹配属于其父元素的第 n 个子元素，n 可以是数字、关键词或公式。

  :nth-last-child() 选择器：匹配属于其元素的第 n 个子元素的每个元素，不论元素的类型，从最后一个子元素开始计数。n 可以是数字、关键词或公式。

  :nth-of-type(n)：选择器匹配属于父元素的特定类型的第n 个子元素。n 可以是数字、关键词或公式

  :nth-last-of-type(n)：选择器匹配属于父元素的特定类型的第 N 个子元素的每个元素，从最后一个子元素开始计数。n 可以是数字、关键词或公式。

  **状态伪类选择器**

  :checked 匹配用户界面上处于选中状态的元素

  :enabled 匹配用户界面上处于可用状态的元素

  :disabled 匹配用户界面上处于禁用状态的元素

33、CSS3 中过渡和动画的区别和各自适用场景？ 

+ 1.动画循环就用animation。在animation中有一个animation-iteration-count属性可以定义循环次数。transition是执行一次以后就不会执行，但是可以通过transitionEnd事件添加循环，与animation相比animation更加简单明了。

  2.自动触发用animation。当页面中的动画是自己执行的那么我们考虑用animation，因为transition是需要借助伪类、js、@madia触发的。常见的伪类是：hover ，：focus。 常见的js就比如click事件。@media可以用于页面缩小到1000px你可以展示你需要的动画。

  3.复杂的动画用animation。在遇到很复杂的动画那就用animation。因为animation可以定义关键帧。那你就可以控制每一帧的动画效果。简单的动画效果可以用transition，里面有transition-timing-function属性可以展示动画的速度效果。

34、说出你知道的 2D 或 3D 变形函数 ?

+ **2D**

  - translate()移动元素
  - rotate()旋转元素
  - scale()缩放元素
  - skew()倾斜

  **3D**

  translateZ() 3D位移函数

  3D旋转的函数有：rotateX、rotateY、rotateZ、rotate3d

  3D缩放：scaleZ()函数指定一个在z轴上的缩放

35、常见的移动端布局解决方案有哪些？原理如何？ 

+ **固定布局**

  在<head>里把viewport加好，根pc端一样，设想整个网页的宽度为320px居中即可，超出部分留白。

  优点：思路沿用PC端，上手简单。

  缺点：大屏幕手机及手机横屏时，两边是留白较大，且大屏幕手机下看起来页面会特别小，操作的按钮也很小，用户体验较差

  **流式布局**

  流动布局重点就是使用百分比来代替传统px，但是高度大都是用px来固定住，所以在大屏幕的手机下显示效果会变成有些页面元素宽度被拉的很长，但是高度还是和原来一样，
  优点是流动布局可以很好解决自适应需求，缺点是通过大量的百分比布局，会出现兼容性的问题，且更适用于对横向拉伸的设计元素，设计的时候存在很多局限性。

  **响应式做法**

  根据目标用户的访问设备的主要类型做三种或四种布局。
  每种布局有一个区间即可利用媒体查询@media，可以为不同分辨率的设备加载不同的样式。这种方法的优点是可以相对精确的控制显示效果，但可能需要对同一个类书写不同的样式会导致代码比较繁复，后期维护困难。

  **rem布局**

  rem是指相对于根元素的字体大小的单位,即根据html元素的font-size来计算大小。
  比如说html的font-size大小为100px,一个div的width为1rem,则div的width大小为100px。

36、`简述 rem 布局原理？`

+ rem是指相对于根元素的字体大小的单位,即根据html元素的font-size来计算大小。
  比如说html的font-size大小为100px,一个div的width为1rem,则div的width大小为100px。

37、如何处理小于 12px 的字体？

+ 设置字体时，不要小于12px,如果一定要小于12px，使用transform:sacle()进行缩放