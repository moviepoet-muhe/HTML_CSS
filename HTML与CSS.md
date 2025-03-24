#  HTML与CSS

## 一、HTML标记与属性

HTML超文本标记语言

### **标题：h1-h6**

```html
<h1>一级标题</h1> <!-- h1 标签在一个网页中只能用一次，用来放新闻标题或网页的 logo -->
<h2>二级标题</h2> <!-- h2 ~ h6 没有使用次数的限制 -->
<h3>三级标题</h3> <!-- 文字加粗 -->
<h4>四级标题</h4> <!-- 字号逐渐减小 -->
<h5>五级标题</h5> <!-- 独占一行（换行） -->
<h6>六级标题</h6>
```

### **段落：p**

独占一行，自上而下排列，段落之间存在间隙，一般用在新闻段落、文章段落、产品描述信息等等。 

```html
<p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。</p>
<p>Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式JavaScript框架。</p> 
```

### **换行：br、水平线：hr**

单标记，独占一行，自上而下排列

```html
<body>
  第一行内容
  <br>
  <br>
  第二行内容
  <hr>
</body>
```

### **文本格式化标记**

```html
<!-- strong、em、ins、del 标签自带强调含义（语义） -->
<!-- 横向排列 -->
<strong>strong 加粗</strong>     
<b>b 加粗</b>    
<em>em 倾斜</em>
<i>i 倾斜</i>
<ins>ins 下划线</ins>
<u>u 下划线</u>
<del>del 删除线</del>
<s>s 删除线</s>
```

### **下角标：sub、上角标：sup**

```html
<p>26<sup>o</sup>C</p>
<p>h<sub>2</sub>o</p>
```

### **图像：img**

横向排列的，作用：在网页中插入图片，src用于指定图像的位置和名称，是 img 的必须属性。 

```html
<!-- 以前网速慢，可能导致图片加载不出来，不想影响网页内容的浏览，用alt替换 -->
  <img src="./cat1.jpg" alt="这是一只猫">
  <img src="./dog.jpg" title="这是一只狗"> <!--当鼠标悬停图片上显示一个标题-->
  <!-- 浏览器缩放图片，默认是等比例缩放 图片的宽度与高度 -->
  <img src="./cat.jpg" width="100" height="600">
```

### **超链接：a**

作用：点击跳转到其他页面。 

**href** 属性值是跳转地址，是超链接的必须属性。

超链接默认是在当前窗口跳转页面，添加 **target="_blank"** 实现**新窗口**打开页面。

拓展：开发初期，不确定跳转地址，则 href 属性值写为 **#**，表示**空链接**，页面不会跳转，在当前页面刷新一次。

```html
<body>
<!-- target="_self | _blank" 是否新窗口打开 _self 默认值（当前的窗口） _blank 新窗口打开跳转 -->
  <a href="https://www.baidu.com/">跳转到百度</a>
  <!-- 跳转到本地文件：相对路径查找 --> 
  <!-- target="_blank" 新窗口跳转页面 --> 
  <a href="./01-标签的写法.html" target="_blank">跳转到01-标签的写法</a>
  <!-- 开发初期，不知道超链接的跳转地址，href属性值写#，表示空链接，不会跳转 -->
  <a href="#">空链接</a>
</body>
```

### **无序列表：ul / li**

独占一行，自上而下排列的

```html
<ul>
    <li>列表条目1</li>
    <li>列表条目2</li>
    <li>列表条目3</li>
</ul>
```

### **有序列表：ol / li**

独占一行，自上而下排列的

```html
  <ol>
    <li>步骤1</li>
    <li>步骤2</li>
    <li>步骤3</li>
  </ol>
```

### **自定义列表：dl / dt / dd**

独占一行，自上而下排列的

```html
<dl> <!-- dl 是定义列表 -->
    <dt>服务中心</dt> <!-- dt 是定义列表的标题 -->
    <dd>申请售后</dd> <!-- dd 是定义列表的描述 / 详情 -->
    <dd>售后政策</dd>
</dl>
```

### **表格：table / tr / td**

独占一行，自上而下排列。

合并单元格

1. 明确合并的目标
2. 保留**最左最上**的单元格，添加属性（取值是**数字**，表示需要**合并的单元格数量**）
   * **跨行合并**，保留最上单元格，添加属性 **rowspan**
   * **跨列合并**，保留最左单元格，添加属性 **colspan**
3. 删除其他单元格

```html
<table border="1" bgcolor="red" width="100" height="100" 
cellspacing="10" cellpadding=“2” align="center" rules="all">  
    
<!-- 表格默认没有边框线，border属性可以为表格添加边框线。 bgcolor：表格背景颜色。
cellpadding：单元格里的内容与单元格边框的间隙。cellspacing：单元格与单元格之间的间隙 

<!-- align：表格水平对齐方式，如果设置到table上面表示的是整个表格的水平对齐，如果设置到行和列上面表示的是行和列内容的水平对齐方式。-->
<!-- rules="none | groups | rows | cols | all" 控制表格中边框（线条）如何显示-->

<!-- 表格标题。caption 标记必须放在表格标记内部，默认带了水平居中效果 -->
<caption>学员信息统计</caption>
    
<thead>  <!-- 表头 -->
  <tr valign="top"> <!-- valign：表格的垂直对齐方式，只是针对于行和列-->
    <th>姓名</th>
    <th>语文</th>
    <th>数学</th>
    <th>总分</th>
  </tr>
</thead>
<tbody>  <!-- 表体 -->
  <tr>
    <td>张三</td>
    <td>99</td>
    <td rowspan="2">100</td>
    <td>199</td>
  </tr>
  <tr>
    <td>李四</td>
    <td>98</td>
    <!-- <td>100</td> -->
    <td>198</td>
  </tr>
</tbody>
<tfoot>  <!-- 表尾 -->
  <tr>
    <td>总结</td>
    <td colspan="3">全市第一</td>
    <!-- <td>全市第一</td>
     <td>全市第一</td> -->
  </tr>
</tfoot>
</table>
```

### **表单：form**

独占一行，自上而下排列。作用：收集用户信息。

使用场景：

* 登录页面
* 注册页面
* 搜索区域

```html
<form action="表单请求地址（了解）" method="get（默认，向服务器获取数据，安全性较低，内容可以在url地址看到，数据量大小有限定，一般是2-4kb左右，传输速度比post快） | post（向服务器传输数据，安全性较高，因为它是通过http post 机制加密过的，数据量大小理论上没有限定的，传输速率比get慢）"></form>
```

**input：文本框**

横向排列

```html
<!-- placeholder 占位文本：提示信息，文本框和密码框都可以使用 -->
文本框：<input type="text" placeholder="提示信息"> 
密码框：<input type="password">
单选框：
<input type="radio" name="gender"> 男 <!-- 禁用：disabled -->
<input type="radio" name="gender" checked> 女  <!-- 默认选中：checked -->
多选框：<input type="checkbox" checked>

<!-- 浏览器优先生效input默认宽度，重置宽度 width: 0; -->
input { flex: 1; width: 0;}

<!-- H5新增表单 -->
 <!-- autocomplete 默认关闭输入框的历史记录提示功能 off 关闭 on 开 -->
    <form autocomplete="off">
        
         <input type="file" multiple> <!-- 上传文件 multiple 可以实现多选功能-->
        
        <!-- autofocus 默认打开网页会自动获取焦点，一般给第一个表单框使用 -->
        <!-- 注意点：当表单设置了 name 属性和值后，默认会开启历史记录功能（之前输入过的内容，当获取焦点时会自动提示） -->
        <input type="text" required autofocus name="username">
        <input type="password" name="password"> 
        
         <input type="email" multiple required> <!-- 邮箱地址 required 非空验证-->
         <input type="range" value="10"> <!-- 进度条 -->
         <input type="color" > <!-- 取色器 -->
         <input type="tel"> <!-- 电话号码 -->
         <input type="search"> <!-- 搜索 -->

        <!-- 日历 -->
        <input type="date" value="2025-01-01">
        <input type="week">
        <input type="month">
        <input type="time"> 

        <!-- maxlength 最大字符长度  minlength 最小字符的长度 -->
         <input type="text" maxlength="10" minlength="2"> 

        <!-- 数字 min 最小值  max 最大值 step 间隔 -->
         <input type="number" min="10" step="10" max="100"> 

        <input type="url"><!-- 网站网址 -->

        <input type="submit">
    </form>
```

**select：下拉菜单**

select 嵌套 option，select 是下拉菜单整体，option是下拉菜单的每一项。

```html
<select>
	<option value="北京">北京</option><!-- option 下拉菜单的选项 -->
	<option>上海</option>  <!-- 选项标记设置的value是给js用的，中间的内容文字是给用户看的 -->
	<option>广州</option>
	<option>深圳</option>
	<option selected>武汉</option>   <!-- selected 属性实现默认选中功能 -->
</select>
```

**textarea：文本域**

```html
<!-- 工作中，使用 CSS 禁用右下角的拖拽功能；使用 CSS 设置尺寸 -->
<textarea rows="10" cols="100" style="resize: none" >请输入评论</textarea>
<!-- cols 字符的宽度（一行可以放多少文字）rows 字符的高度 （整个框可以放多少行） -->
```

**label：标签**

作用：网页中，某个标签的说明文本。 

经验：用 label 标签绑定文字和表单控件的关系，增大表单控件的点击范围。 、

```html
写法一：
label 标签只包裹内容，不包裹表单控件。
设置 label 标签的 for 属性值 和表单控件的 id 属性值相同。
<input type="radio" id="man"><label for="man">男</label>
写法二：
使用 label 标签包裹文字和表单控件，不需要属性。
<label><input type="radio">女</label>
```

提示：支持 label 标签增大点击范围的表单控件：文本框、密码框、上传文件、单选框、多选框、下拉菜单、文本域等等。 

**button：按钮**

```html
<body>
  <!-- form 表单区域 -->
  <!-- action="" 发送数据的地址 -->
  <form action="">
    用户名：<input type="text">
    密码：<input type="password">
    <!-- 如果省略 type 属性，功能是 提交 --> 
    <input type="submit" value="免费注册"> 如果不设置 value 属性，那么默认会自带 "提交" 的文本提示 
    <input type="reset"> 重置按钮,如果不设置 value 属性，那么默认会自带 "重置" 的文本
      
    <button type="button">普通按钮</button>
  </form>
```

### **无语义的布局标签 span、div**

作用：布局网页（划分网页区域，摆放内容）

```html
<div>div 标签，独占一行</div>
<span>span 文本节点标签，不换行</span> <!-- 默认没有任何样式，比较适合把某几个字或者一小段内容包裹起来单独设置样式 -->
```

**字符实体**

| 字符 | 字符实体 |
| ---- | -------- |
| <    | &lt      |
| >    | &gt      |
| &    | &amp     |
| 空格 | &nbsp    |
| ×    | &times   |
| +    | &plus    |
| -    | &minus   |

### **HTML5新增标记**

独占一行，自上而下排列。

```html
<header>网页头部标记</header>
<nav>导航标记</nav>
<main>主要内容标记</main>
<article>文章标记</article>
<section>块或者区域标记</section>
<aside>侧边栏标记</aside>
<footer>网页尾部标记</footer>
<!-- 图文结构标记 -->
<figure>
    <img src="" alt="">
    <figcaption>图文标题标记</figcaption>
</figure>
```

```html

    <!-- 定义日期或时间 内联标记-->
     <time datetime="2025-01-01">元旦</time> 
     <p>王江早上<time>10:00</time>起床</p> 
     <time>2025-01-01 9:00:00</time> 

    <!-- 高亮显示 内联标记 -->
     <p>震惊，<mark>王江</mark>竟然做出了这样的事情</p>
    
    <!-- 地址 块标记 -->
     <address>武侯区夏家河大厦三楼</address> 
    
    <!-- 对话框，具有语义化 块标记 -->
     <dialog open>This is an open dialog window</dialog> 

    <!-- 详情标记 块标记，默认多了一个按钮隐藏和显示 -->
     <details>王江...牛逼历史</details> 

    <!-- 多媒体标记 块标记-->
    <!-- controls 控件：控制进度条、声音、放大、暂停/播放 -->
    <!-- loop 循环播放 -->
    <!-- autoplay 自动播放（有些浏览器为了用户体验，会禁用自动播放功能） -->
    <!-- muted 静音功能 -->
    <!-- poster 封面 -->
     <video src="./videos/3theA.mp4" controls loop autoplay poster="./img/02.jpg"></video> 

    <!-- video 标记只支持三种视频格式 mp4、webm、ogg -->
        <video controls loop autoplay poster="./img/02.jpg">
            <source src="./videos/3theB.mp4" type="video/mp4"/>
            <source src="./videos/3theB.mp4" type="video/webm"/>
            <source src="./videos/3theB.mp4" type="video/ogg"/>
        </video> 
    
    <!-- 音频 -->
     <audio src="./music/赵大格 - 我在人民广场吃炸鸡 (Live).mp3" controls autoplay muted></audio> 
    
    <!--定义嵌入的内容，比如插件,播放视频和音频 -->
    <embed src="./videos/dongbei.mp4"/> 
    <embed src="./music/阿杜 - 他一定很爱你.flac">
<canvas> 标签定义图形，比如图表和其他图像。该标签基于 JavaScript 的绘图 API
```



## 二、CSS各类属性

层叠样式表 (Cascading Style Sheets，缩写为 CSS），是一种 **样式表** 语言，用来**描述 HTML 文档的呈现**（**美化内容**）。

### 1、引入方式

* **内部**样式表：学习使用
  * CSS 代码写在 style 标签里面
* **外部**样式表：开发使用
  * CSS 代码写在单独的 CSS 文件中（**.css**）
  * 在 HTML 使用 link 标签引入

```html
<link rel="stylesheet" href="./my.css">
```

* **行内**样式：配合 JavaScript 使用
  * CSS 写在标签的 style 属性值里

```html
<div style="color: red; font-size:20px;">这是 div 标签</div>
```

### 2、选择器

作用：**查找标签**，设置样式。 

#### 标签选择器

标签选择器：使用**标签名**作为选择器 → 选中**同名标签设置相同的样式**。

例如：p, h1, div, a, img......

```html
<style>
  p {
    color: red;
  }
</style>
```

> 注意：标签选择器**无法差异化**同名标签的显示效果。

#### 类选择器

作用：查找标签，**差异化**设置标签的显示效果。

步骤：

* 定义类选择器 → **.类名**
* 使用类选择器 → 标签添加 **class="类名"**

```html
<style>
  /* 定义类选择器 */
  .red {
    color: red;
  }
</style>
<!-- 使用类选择器 -->
<div class="red">这是 div 标签</div>
<div class="red size">div 标签</div>
```

注意：

* 类名**自定义**，不要用纯数字或中文，尽量用英文命名
* 一个类选择器**可以供多个标签使用**
* **一个标签可以使用多个类名**，类名之间用**空格**隔开

> 开发习惯：类名见名知意，多个单词可以用 - 连接，例如：news-hd。

#### id选择器

作用：查找标签，差异化设置标签的显示效果。

场景：id 选择器一般**配合 JavaScript** 使用，很少用来设置 CSS 样式

步骤：

* 定义 id 选择器 → #id名
* 使用 id 选择器 → 标签添加 id= "id名"

```html
<style>
  /* 定义 id 选择器 */
  #red {
    color: red;
  }
</style>
<!-- 使用 id 选择器 -->
<div id="red">这是 div 标签</div>
```

> 规则：同一个 id 选择器在一个页面只能使用一次。

#### 通配符选择器

作用：查找页面**所有**标签，设置相同样式。

通配符选择器： ***，不需要调用**，浏览器自动查找页面所有标签，设置相同的样式

```css
* {
  color: red;
}

*{
  margin: 0;
  padding: 0;
}
```

> 经验：通配符选择器可以用于**清除标签的默认样式**，例如：标签默认的外边距、内边距。

#### 后代选择器

后代选择器：**选中某元素的后代元素**。

选择器写法：父选择器  子选择器 { CSS 属性}，父子选择器之间用**空格**隔开。

```html
<style>
  div span {
    color: red;
  }
</style>
<span> span 标签</span>
<div>
  <span>这是 div 的儿子 span</span >
</div>
```

#### 子代选择器

子代选择器：选中某元素的子代元素（**最近的子级**）。

选择器写法：父选择器 > 子选择器 { CSS 属性}，父子选择器之间用 **>** 隔开。

```html
<style>
  div > span {
    color: red;
  }
</style>

<div>
  <span>这是 div 里面的 span</span>
  <p>
    <span>这是 div 里面的 p 里面的 span</span>
  </p>
</div>

```

#### 并集选择器

并集选择器：选中**多组标签**设置**相同**的样式。

选择器写法：选择器1, 选择器2, …, 选择器N { CSS 属性}，选择器之间用 **,** 隔开。

```html
<style>
  div,
  p,
  span {
    color: red;
  }
</style>

<div> div 标签</div>
<p>p 标签</p>
<span>span 标签</span>
```

#### 交集选择器

交集选择器：选中**同时满足多个条件**的元素。

选择器写法：选择器1选择器2 { CSS 属性}，选择器之间连写，没有任何符号。 

```html
<style>
  p.box {
  color: red;
}
</style>

<p class="box">p 标签，使用了类选择器 box</p>
<p>p 标签</p>
<div class="box">div 标签，使用了类选择器 box</div>
```

> 注意：如果交集选择器中有标签选择器，标签选择器必须书写在最前面。 

#### 伪类选择器

伪类选择器：伪类表示元素**状态**，选中元素的某个状态设置样式。

鼠标悬停状态：**选择器:hover { CSS 属性 }**

```html
<style>
  a:hover {
    color: red;
  }
  .box:hover {
    color: green;
  }
</style>

<a href="#">a 标签</a>
<div class="box">div 标签</div>
```

#### 超链接伪类

| 选择器   | 作用         |
| -------- | ------------ |
| :link    | 访问前       |
| :visited | 访问后       |
| :hover   | 鼠标悬停     |
| :active  | 点击时(激活) |

> 提示：如果要给超链接设置以上四个状态，需要按 LVHA 的顺序书写。 
>
> 经验：工作中，一个 a 标签选择器设置超链接的样式， hover状态特殊设置 

#### 结构序列伪类选择器

作用：根据元素的**结构关系**查找元素。 

| 选择器         | 说明                                 |
| -------------- | ------------------------------------ |
| E:first-child  | 查找第一个E元素                      |
| E:last-child   | 查找最后一个E元素                    |
| E:nth-child(N) | 查找第 N 个E元素(第一个元素 N 值为1) |

**:nth-child(公式)**

| 功能                | 公式      |
| ------------------- | --------- |
| 偶数标签            | 2n        |
| 奇数标签            | 2n+1;2n-1 |
| 找到5的倍数的标签   | 5n        |
| 找到第5个以后的标签 | n+5       |
| 找到第5个以前的标签 | -n+5      |

> 提示：公式中的n取值从 **0** 开始。 

1、选中同级别的，不能被其他类型的标记给隔开。

```css
/* 选中 ul 下的第一个 li 标记 */
ul li:first-child
/* 选中 ul 下的第几个 li 标记 */
ul li:nth-child(3)
/* 选中 ul 下的倒数第几个 li 标记 */
ul li:nth-last-child(3)
/* 选中 ul 下的最后一个 li 标记 */
ul li:last-child
```

2、选中同类型的，可以被其他类型的标记给隔开。

```css
ul li:first-of-type
ul li:nth-of-type(2)
ul li:last-of-type
ul li:nth-last-of-type(3)
```

3、选中父元素中唯一的子元素标记。

```css
p:only-child
p:only-of-type
```

4、注意点：序列选择器推荐使用的话，一般用在内层元素，不要在最外层的元素里面使用。

#### 伪元素选择器

伪元素选择器也叫做伪对象选择器。

作用：通过 css 选择器的形式为标记创建**虚拟元素**（伪元素），用来**摆放装饰性的内容**。 默认添加的元素类型是内联（行内）。

```css
/* 默认会显示在标记子元素的前面 */
div::before {
  content: "before 伪元素";
}

/* 默认会显示在标记子元素的后面 */
div::after {
  content: "after 伪元素";
}

/* 只对第一行起作用 */
div::first-line{
    font-size: 20px;
    color: red;
} 
/* 只对第一行里面的第一个字起作用 */
div::first-letter{
    font-size: 20px;
    color: red;
}

/* 伪元素实现三角 */
div::after{
    content: "";
    /* transparent 透明 */
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    border-bottom: 5px solid transparent;
    border-top: 5px solid purple;
}
/* 代码实现三角 */
 div{   
    border-left: 20px solid transparent;
    border-right: 20px solid transparent;
    border-bottom: 20px solid transparent;
    border-top: 20px solid purple;
    width: 0;
    height: 0;
}
/* 伪元素实现边框 */
div::after{
    content: "";
    width: 1px;
    height: 10px;
    background-color: orange;
}
```

注意点：

* 必须设置 **content: ””属性**，用来 设置伪元素的内容，如果没有内容，则**引号留空**即可
* 伪元素默认是**行内**显示模式
* **权重和标签选择器相同**

#### 属性选择器

通过标记自身携带的默认属性来选取元素给其设置样式，可以减少对类名的依赖。

```html
    <style>
        /* 通过标记的属性名来选取元素 */
         input[type]{
            border: 1px solid red;
        } 

         input[name]{
            border: 1px solid red;
        } 

        /* 通过标记的属性的属性值来选取元素（推荐） */
        input[type="text"]{
            border: 1px solid red;
        }
        input[type="password"]{
            border: 1px solid orange;
        }

        /* 通过标记的属性的属性值开头字符选取元素 */
        a[href^="J"]{
            color: red;
        }
        /* 通过标记的属性的属性值结尾字符选取元素 */
        a[href$="m"]{
            color: yellow;
        }
    </style>
</head>
<body>
    <input type="text" value="" name="username">
    <input type="password" value="" name="userpwd">
    <input type="reset">
    <input type="submit">
    <input type="button" value="免费注册">

    <a href="#">空链接</a>
    <a href="JavaScript:;">空链接</a>
    <a href="https://www.jd.com">jd</a>
    <a href="JavaScript:;">空链接</a>
    <a href="https://www.baidu.com">jd</a>
</body>
</html>
```

#### 根选择器:root

```css
/* root 根选择器里面可以定义变量 */
:root{
    --wj-orange--: hotpink;
}
h1{
    /* var 函数 可以使用定义在根选择器里面的变量 */
    color: var(--wj-orange--);
}
p{
    color: var(--wj-orange--);
}
div{
    color: var(--wj-orange--);
}
```



### 4、文字控制属性

#### （1）字体大小：font-size

**font-size**：文字尺寸，PC 端网页最常用的单位 **px**

```css
p {
  font-size: 30px;
}
```

> 经验：谷歌浏览器默认字号是16px。

#### （2）字体加粗：font-weight

**font-weight**：文字加粗

```css
p {
  /* 数字（开发使用）*/
  font-weight: 400;/*正常*/
  font-weight: 700;/*加粗*/
  /*关键字*/
  font-weight: normal;/*正常*/
  font-weight: bold;/*加粗*/
  font-weight: bolder;/*加粗*/
}
```

#### （3）字体是否倾斜：font-style

```css
p {
  font-style:normal; /* 正常（不倾斜）*/
  font-style:italic; /* 斜体字*/
  font-style:oblique;/* 向右倾斜（常用）*/
}
```

#### （4）行高：line-height

设置多行文本的间距

```css
line-height: 30px;
/* 当前标签字体大小为16px */
line-height: 2; /* 当前标签font-size属性值的倍数=32px */
```

> 行高的测量方法：从一行文字的最顶端（最底端）量到下一行文字的最顶端（最底端）。 

垂直居中技巧：**行高属性值等于盒子高度属性值**

注意：该技巧适用于单行文字垂直居中效果，行高大于字号 ，字向下移动，行高小于字号，文字向上移动。

```css
div {
  height: 100px;
  background-color: skyblue;
  /* 注意：只能是单行文字垂直居中 */
  line-height: 100px;
}
```

#### （5）字符间距：letter-spacing

```css
letter-spacing: 2px; /* 增加字符间距 */
```

#### （6）字体族：font-family

```css
font-family: "楷体"; /* 中⽂字体需要使⽤引号包裹 */
```

> 拓展（了解）：font-family属性值可以书写多个字体名，各个字体名用逗号隔开，执行顺序是从左向右依次查找
>
> *  font-family 属性最后设置一个字体族名，网页开发建议使用无衬线字体

```css
font-family: "Microsoft YaHei", "Heiti SC", tahoma, arial, "Hiragino Sans GB", "\5B8B\4F53", sans-serif;
/* 多个字体之间使⽤逗号隔开，英⽂字体如果是单个单词的不需要使⽤引号，如果是多个单词组成的字体需要使⽤引号 */
```

#### （7）font：复合属性

使用场景：设置网页文字公共样式 

```css
body {
font: 12px/1.5 Microsoft YaHei,Heiti sc,tahoma,arial,Hiragino sans GB,"\5B8B\4F53",sans-serif;
color:【#666;
}
```

复合属性：属性的简写方式，**一个属性对应多个值的写法**，各个属性值之间用**空格**隔开。

**font: 是否倾斜  是否加粗  字号/行高 字体（必须按顺序书写）**

```css
div {
  font: italic 700 30px/2 楷体;
}
```

> 注意：字号和字体值必须书写，否则 font 属性不生效 。

#### （8）文本缩进：text-indent

```css
p {
  font-size: 16px;
  text-indent: 32px;/*数字 + px*/
  text-indent: 2em;/*推荐：1em = 当前标签的字号大小*/
}
```

#### （9）文本对齐方式：text-align

控制内容水平对齐方式

| 属性值  | 效果               |
| ------- | ------------------ |
| left    | 左对齐（默认）     |
| center  | 居中对齐           |
| right   | 右对齐             |
| justify | 文本的左右两端对齐 |

> text-align本质是控制内容的对齐方式，属性要设置给内容的父级。 

#### （11）文本修饰线：text-decoration

| 属性值       | 效果   |
| ------------ | ------ |
| none         | 无     |
| underline    | 下划线 |
| line-through | 删除线 |
| overline     | 上划线 |

#### （12）color：文字颜色

| 颜色表示方式   | 属性值           | 说明                              | 使用场景               |
| -------------- | ---------------- | --------------------------------- | ---------------------- |
| 颜色关键字     | 颜色英文单词     | green、 blue...red、              | 学习测试               |
| rgb表示法      | rgb(r, g, b)     | r,g,b表示红绿蓝三原色，取值:0-255 | 了解                   |
| rgba表示法     | rgba(r, g, b, a) | a表示透明度，取值:0-1             | 开发使用，实现透明色   |
| 十六进制表示法 | #RRGGBB          | #000000，#ffcc00，简写:#000，#fc0 | 开发使用(从设计稿复制) |

> 提示：只要属性值为颜色，都可以使用上述四种颜色表示方式，例如：背景色。 

#### （13）列表样式：list-style

```css
li{
    list-style: none; /* 取消列表符号 */
    list-style-type: disc;  /* disc 实心圆 */
    list-style-type: square;  /* square 小方块 */
    list-style-type: circle;  /* circle 空心圆 */            
    list-style-position: inside; /* 列表符号的位置 */
    list-style-type: none; /* === list-style: none; */
}
```

### 5、盒子尺寸和背景色

|      属性名      | 作用   |
| :--------------: | ------ |
|      width       | 宽度   |
|      height      | 高度   |
| background-color | 背景色 |

### 6、边框线：border

**四个方向：border**

属性名：**border**（bd）

属性值：边框线粗细  线条样式  颜色（不区分顺序）

```css
div {
  border: 5px solid brown; /* solid 实线  dashed 虚线  dotted 点线 */
  width: 200px;
  height: 200px;
  background-color: pink;
}
div2 {
  border: 5px double brown; /* double：双线 */
}
```

**单方向边框线：border-方位名词**

属性名：**border-方位名词**（bd+方位名词首字母，例如，bdl）

属性值：边框线粗细  线条样式  颜色（不区分顺序）

```css
div {
  border-top: 2px solid red;
  border-right: 3px dashed green;
  border-bottom: 4px dotted blue;
  border-left: 5px solid orange;
  width: 200px;
  height: 200px;
  background-color: pink;
}
```

**取消边框线：border: none | 0;**

```css
div {
  border-top: none;
  border-top: 0;
}
```

### 7、背景属性：background

**背景图：background-image**

```css
div {
  width: 400px;
  height: 400px;
  background-image: url(./images/1.png);
}
```

> 提示：背景图默认有**平铺（复制）效果**。 

**平铺方式：background-repeat**

| 属性值    | 效果           |
| --------- | -------------- |
| no-repeat | 不平铺         |
| repeat    | 平铺(默认效果) |
| repeat-X  | 水平方向平铺   |
| repeat-y  | 垂直方向平铺   |

**背景图位置：background-position**

属性值：水平方向位置 垂直方向位置

- 关键字

| 关键字 | 位置 |
| ------ | ---- |
| left   | 左侧 |
| right  | 右侧 |
| center | 居中 |
| top    | 顶部 |
| bottom | 底部 |

* 坐标
  * 水平：正数向右；负数向左
  * 垂直：正数向下；负数向上

> 提示：
>
> * 关键字取值方式写法，可以颠倒取值顺序
> * 可以只写一个关键字，另一个方向默认为居中；数字只写一个值表示水平方向，垂直方向为居中

**背景图缩放：background-size**

作用：设置背景图大小

常用属性值：

* 关键字
  *  cover：等比例缩放背景图片以完全覆盖背景区，可能背景图片部分看不见
  *  contain：等比例缩放背景图片以完全装入背景区，可能背景区部分空白

* 百分比：根据盒子尺寸计算图片大小
* 数字 + 单位（例如：px）

```css
div {
  width: 500px;
  height: 400px;
  background-color: pink;
  background-image: url(./images/1.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-size: contain;
}
```

> 提示：工作中，**图片比例与盒子比例相同**，使用 cover 或 contain 缩放背景图效果相同。

**背景图固定：background-attachment**

作用：背景不会随着元素的内容滚动。

属性值：**fixed**

```css
body {
  background-image: url(./images/bg.jpg);
  background-repeat: no-repeat;
  background-attachment: fixed;
}
```

**背景复合属性：background**

属性值：背景色 背景图 背景图平铺方式 背景图位置/背景图缩放  背景图固定（**空格隔开各个属性值，不区分顺序**）

```css
div {
  width: 400px;
  height: 400px;

  background: pink url(./images/1.png) no-repeat right center/cover fixed;
}
```

### 8、圆角 border-radius

设置元素的外边框为圆角。

属性值：数字+px / 百分比，属性值是圆角半径。

| 取值个数 | 示例                                 | 含义                                               |
| -------- | ------------------------------------ | -------------------------------------------------- |
| 一个值   | border-radius: 10px ;                | 四个角均为10px                                     |
| 四个值   | border-radius: 10px 20px 40px 80px ; | 左上: 10px; 右上: 20px ; 右下 : 40px ; 左下 : 80px |
| 三个值   | border-radius: 10px 40px 80px ;      | 左上: 10px ; 右上+左下 : 40px ; 右下 : 80px        |
| 两个值   | border-radius: 10px  80px ;          | 左上+右下: 10px ; 右上 + 左下 : 80px               |

> 技巧：从左上角开始顺时针赋值，当前角没有数值则与对角取值相同。 

* 正圆形状：给正方形盒子设置圆角属性值为 **宽高的一半 / 50%**

```css
img {
  width: 200px;
  height: 200px;
  border-radius: 100px;
  border-radius: 50%;
}
```

* 胶囊形状：给长方形盒子设置圆角属性值为 盒子高度的一半 

```css
div {
  width: 200px;
  height: 80px;
  background-color: orange;
  border-radius: 40px;
}
```

### 9、文字与盒子阴影  box-shadow  text-shadow

给元素设置阴影效果

属性值：X 轴偏移量  Y 轴偏移量  模糊半径  扩散半径  颜色  内外阴影

* X 轴偏移量 和 Y 轴偏移量 必须书写
* 默认是外阴影，内阴影需要添加 inset

```css
div {
  width: 200px;
  height: 80px;
  background-color: orange;
  box-shadow: 2px 5px 10px 0 rgba(0, 0, 0, 0.5) inset;
}
```

### 10、CSS修饰属性

#### （1）垂直对齐方式：vertical-align

| 属性值   | 效果           |
| -------- | -------------- |
| baseline | 基线对齐(默认) |
| top      | 顶部对齐       |
| middle   | 居中对齐       |
| bottom   | 底部对齐       |

#### （2）过渡：transition（复合属性）

作用：可以为一个元素在不同状态之间切换的时候添加**过渡效果**

属性值：**过渡的属性  花费时间 (s)**

提示：

* 过渡的属性可以是具体的 CSS 属性
* 也可以为 all（两个状态属性值不同的所有属性，都产生过渡效果）
* transition 设置给元素本身

```css
img {
  width: 200px;
  height: 200px;
  transition: all 1s;
}
img:hover {
  width: 500px;
  height: 500px;
}

transition: all .2s linear; 匀速过渡
transition: all .2s ease; 开始慢 → 加速 → 结束慢 逐渐慢。是 CSS 默认的过渡曲线，适用于大多数场景。
transition: all .2s ease-in;加速
transition: all .2s ease-out; 减速
transition: all .2s ease-in-out;  开始慢 → 加速 → 减速。
```

```css
过渡属性分写形式：
transition-property：检索或设置对象中的参与过渡的属性
transition-duration：检索或设置对象过渡的持续时间
transition-delay：检索或设置对象延迟过渡的时间
transition-timing-function：检索或设置对象中过渡的动画类型
简写：
transition:all(全部或所有)/具体属性值    运动时间s/ms   延迟时间s/ms   动画类型;
```



#### （3）透明度：opacity

作用：设置**整个元素的透明度**（包含背景和内容）

属性值：0 – 1

* 0：完全透明（元素不可见）
* 1：不透明
* 0-1之间小数：半透明

问题：子元素会继承父元素的透明度

rgba() 函数：透明度不会被子元素所继承

#### （4）光标类型：cursor

作用：鼠标悬停在元素上时指针显示样式

| 属性值  | 效果                         |
| ------- | ---------------------------- |
| default | 默认值，通常是箭头           |
| pointer | 小手效果，提示用户可以点击   |
| text    | 工字型，提示用户可以选择文字 |
| move    | 十字光标，提示用户可以移动   |

### 11、CSS特性

CSS特性：化简代码 / 定位问题，并解决问题

* 继承性
* 层叠性
* 优先级

#### 继承性

继承性：子级默认继承父级的**文字控制属性**。 

> 注意：如果标签有默认文字样式会继承失败。 例如：a 标签的颜色、标题的字体大小。

#### 层叠性

特点：

* 相同的属性会覆盖：**后面的 CSS 属性覆盖前面的 CSS 属性**
* 不同的属性会叠加：**不同的 CSS 属性都生效**

```html
<style>
  div {
    color: red;
    font-weight: 700;
  }
  div {
    color: green;
    font-size: 30px;
  }
</style>

<div>div 标签</div>
```

> 注意：选择器类型相同则遵循层叠性，否则按选择器优先级判断。 

#### 优先级

优先级：也叫权重，当一个标签**使用了多种选择器时**，基于不同种类的选择器的**匹配规则**。

**基础选择器**

- 规则：选择器**优先级高的样式生效**。（选中标签的范围越大，优先级越低）

- 公式：通配符选择器 < 标签选择器 < 类选择器 < id选择器 < 行内样式 < !important

**复合选择器-叠加**

叠加计算：如果是复合选择器，则需要**权重叠加**计算。

规则：

（**行类**样式，**id**选择器个数，**类**选择器个数，**标签**选择器个数）

* 从左向右依次比较选个数，同一级个数多的优先级高，如果个数相同，则向后比较
* **!important 权重最高**
* 继承权重最低 

### 12、锚点

可以在同一个网页中不同的位置进行跳转。也是超链接的一种应用类型。

```html
<标记 id="名称"></标记>
<a href="#名称"></a>
```



## 三、盒模型

作用：布局网页，摆放盒子和内容。

### 1、盒子模型-组成

**标准盒模型**（W3C）

 标准盒模型计算 ：

盒模型的宽度 = 左右margin + 左右padding + 左右border + width 

盒模型的高度 = 上下margin + 上下padding + 上下border + height 

**怪异盒模型**（IE）

怪异盒模型计算 ：

盒模型的宽度 = 左右margin + width（包含了padding 和 border） 

盒模型的高度 = 上下margin + height（包含了padding 和 border） 

当使用了 border 和 padding 属性后，怪异盒模型会自动计算宽度和高度，不需要手动去减去对应的值 。

```css
box-sizing: border-box（怪异盒模型） | content-box（默认值，标准盒模型）；
```

### 2、元素类型 显示模式

css 把 html 标记划分成了三种类型，分别是块级（block）元素、内联（inline）元素、内联块（inline-block） 元素。当然也有人把元素划分成了两种类型，分别是块级元素、内联元素（包含内联块元素）。

**块级元素（block）**

- 独占⼀行，自上而下排列，可以设置宽度（宽度默认是父级的100%）和高度，⼀般作为其他元素的容器。

例如： div、h1-h6、p、ul、ol、li、form、table、dl、dt、dd、section、header、footer、main... 

- p 标记里面不能包含其他的块级元素，浏览器在解析的时候不会把其他的块级元素放在p元素内部。

**行内（内联）元素（inline）**

- 横向排列，一行可以显示多个，不能设置宽度和高度，宽高尺寸由内容撑开。

例如：a、b、strong、i、em、span... 

- margin和padding上下值对内联元素是存在问题的：margin上下值无用，padding上下值显示位置不对。
- a 标记可以包含在其他块级元素的外层，但是其他的内联元素不建议包含块级元素。

**行内块（内联块）元素（inline-block）**

- 横向排列，一行可以显示多个，可以设置宽度和高度，宽高尺寸也可以由内容撑开。

例如：img、input所有的类型、select、 textarea... 

### 3、转换元素类型 显示模式（display）

元素类型转换在实际的开发中，有时候需要给内联元素设置宽度和高度，但是本身是不能设置的，这个时候就需要使用到元素类型转换属性display 进行元素类型的转换。

- display: block; 把其他类型转成块级元素 。
- display: inline; 把其他类型转成内联（行内）元素。⼀般使用比较少，对内联块元素是不起作用的，因为内联块元素本身存在默认尺存和样式 。
- display: inline-block; 把其他类型转成内联块元素 
- dispaly: none; 可以把显示的元素隐藏

**组合使用：**

- dispaly: none; 可以把显示的元素隐藏。
- display: block; 把其他类型转成块级元素。可以把隐藏的元素显示 。

**display 需要了解的属性值：**

- display属性链接：https://www.runoob.com/cssref/pr-class-display.html
- table 表格类型
- inline-table 内联表格类型 
- table-cell 单元格类型 
- table-caption 表格标题类型 
- inherit 继承，从父元素上⾯继承⼀些属性（默认继承，因此使用较少） 
- list-item 列表类型

### 4、内边距：padding

作用：设置 内容 与 盒子边缘 之间的距离。

* 属性名：padding / padding-方位名词

> 提示：添加 padding 会撑大盒子。

* padding 多值写法

| 取值个数 | 示例                         | 含义                            |
| -------- | ---------------------------- | ------------------------------- |
| 一个值   | padding: 10px;               | 四个方向内边距均为10px          |
| 两个值   | padding:10px 80px;           | 上下:10px;左右:80px             |
| 三个值   | padding:10px 40px 80px;      | 上:10px;左右:40px;下:80px       |
| 四个值   | padding: 10px 20px40px 80px; | 上:10px;右:20px;下:40px;左:80px |

> 技巧：从**上**开始**顺时针**赋值，当前方向没有数值则与**对面取值相同**。 

### 5、尺寸计算：box-sizing: border-box

给盒子加 border / padding 会撑大盒子

解决：

* 手动做减法，减掉 border / padding 的尺寸。（calc() 方法是 css3 版本里面新增的，可以用来进行四则运算）
* 內减模式：**box-sizing: border-box**

### 6、外边距 margin

作用：拉开两个盒子之间的距离

提示：与 padding 属性值写法、含义相同

margin负值``margin-left: -1px;``实现边框重叠。

### 7、版心居中 margin: 0 auto;

左右 margin 值 为 auto（盒子要有宽度）

### 8、清除默认样式

清除标签默认的样式，比如：默认的内外边距。 

```css
/* 清除默认内外边距 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
/* 清除列表项目符号 */
li {
  list-style: none;
}
```

### 9、元素溢出 overflow

作用：控制溢出元素的内容的显示方式。visible 默认值（没有任何改变）。

overflow: hidden; 作用：

1、内容溢出隐藏

2、清除浮动

3、解决 margin-top 兼容问题

| 属性值 | 效果                                     |
| ------ | ---------------------------------------- |
| hidden | 溢出隐藏                                 |
| scroll | 溢出滚动(无论是否溢出，都显示滚动条位置) |
| auto   | 溢出滚动(溢出才显示滚动条位置)           |

### 10、外边距问题

**合并现象**

场景：**垂直**排列的兄弟元素，上下 **margin** 会**合并**

现象：取两个 margin 中的**较大值生效**

```css
.one {
  margin-bottom: 50px;
}
.two {
  margin-top: 20px;
}
```

**外边距塌陷**

场景：父子级的标签，子级的添加 **上外边距** 会产生**塌陷**问题

现象：**导致父级一起向下移动**

```css
.son {
  margin-top: 50px;
  width: 100px;
  height: 100px;
  background-color: orange;
}
```

解决方法：

* 取消子级margin，父级设置padding
* 父级设置 overflow: hidden
* 父级设置 border-top

### 11、行内元素 – 内外边距问题

场景：行内元素添加 margin 和 padding，无法改变元素垂直位置

解决方法：给行内元素添加 **line-height** 可以改变垂直位置

```css
span {
  /* margin 和 padding 属性，无法改变垂直位置 */
  margin: 50px;
  padding: 20px;
  /* 行高可以改变垂直位置 */
  line-height: 100px;
}
```

## 四、Flex弹性盒布局

### 1、标准流

标准流也叫文档流，指的是标签在页面中**默认的排布规则**，例如：块元素独占一行，行内元素可以一行显示多个。 

### 2、浮动：float

作用：让块元素水平排列。

* **left**：左对齐
* **right**：右对齐

**特点：**

- 浮动后的盒子**顶对齐**
- 浮动后的盒子具备**行内块**特点
- 浮动后的盒子**脱标**，**不占用标准流的位置**

> 如果父级宽度不够，浮动的盒子会掉下来

#### 清除浮动

场景：浮动元素会脱标，如果**父级没有高度**，**子级无法撑开父级高度**（可能导致页面布局错乱）。

解决方法：**清除浮动**（清除浮动带来的影响）。

**(1) 额外标签法**

在**父元素内容的最后**添加一个**块级**元素，设置 CSS 属性 **clear: both** 

```html
<style>
.clearfix {
  clear: both;
}
</style>
<div class="father">
  <div class="left"></div>
  <div class="right"></div>
  <div class="clearfix"></div>
</div>
```

**(2) overfow法**

```css
.father {
  margin: 10px auto;
  width: 1200px;
  background-color: pink;
  overflow: hidden;
}
```

**(5) 万能清除方法**

给父元素设置

```css
.father::after{
    content: "";
    display: block;
    height: 0;
    clear: both;
    visiblity: hidden;
}
```



### 3、Flex弹性盒布局

- Flex 布局也叫**弹性布局**，是浏览器**提倡的布局模型**，非常适合**结构化**布局，提供了强大的空间分布和对齐能力。它是**<span>css3</span>**引入的一种新的布局模式，即伸缩布局盒模型，用来提供一个更有效的方式制定、调整和分布一个容器里的项目布局。
- Flex 模型不会产生浮动布局中脱标现象，布局网页更简单、更灵活。
- 主要思想是让容器有能力让其子项目能够改变其宽度、高度（甚至顺序），以最佳的方式填充可用空间（主要是为了适应所有类型的显示设备和屏幕大小）。flex容器会使子项目扩展来填充可用空间，或缩小他们以防止溢出容器。
- 当把容器转为弹性盒布局后，项目都可以设置宽度和高度，不会受之前元素类型的特性的影响

#### （1）Flex组成

设置方式：给**父**元素设置 **display: flex**，子元素可以自动挤压或拉伸

组成部分：

* 弹性容器 / 伸缩容器（父元素）
* 弹性盒子 / 伸缩项目（子元素）
* 主轴 / X轴：默认在**水平**方
* 侧轴 / 交叉轴 / Y轴：默认在**垂直**方向

#### （2）主轴对齐方式：justify-content

| 属性值        | 效果                                                   |
| ------------- | ------------------------------------------------------ |
| flex-start    | 默认值，弹性盒子从**起点**开始依次排列                 |
| flex-end      | 弹性盒子从**终点**开始依次排列                         |
| center        | 弹性盒子沿主轴**居中**排列                             |
| space-between | 弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子**之间** |
| space-around  | 弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子**两侧** |
| space-evenly  | 弹性盒子沿主轴均匀排列，弹性盒子与容器之间**间距相等** |

#### （3）侧轴对齐方式：align-items、align-self

* align-items：当前弹性容器内**所有**弹性盒子的侧轴对齐方式（给**弹性容器**设置）
* align-self：单独控制**某个弹性盒子**的侧轴对齐方式（给**弹性盒子**设置）
* align-self可以覆盖align-items

| 属性值     | 效果                                                         |
| ---------- | ------------------------------------------------------------ |
| stretch    | 弹性盒子沿着侧轴线被**拉伸至铺满容器**(弹性盒子没有设置侧轴方向尺寸则默认拉伸) |
| center     | 弹性盒子沿侧轴**居中**排列                                   |
| flex-start | 弹性盒子从**起点**开始依次排列                               |
| flex-end   | 弹性盒子从**终点**开始依次排列                               |

#### （4）伸缩流方向：flex-direction

**主轴默认在水平方向，侧轴默认在垂直方向**

| 属性值         | 效果                     |
| -------------- | ------------------------ |
| row            | 水平方向，从左向右(默认) |
| column         | 垂直方向，从上向下       |
| row-reverse    | 水平方向，从右向左       |
| column-reverse | 垂直方向，从下向上       |

#### （5）弹性伸缩比：flex

作用：控制弹性盒子的主轴方向的尺寸。

属性值：整数数字，表示占用**父级剩余尺寸的份数**。

- 情况1：flex 当给项目设置后，可以把项目容器的空间重新分配，把剩余空间占满。其他项目如果没有设置 flex 属性的话，那么它自身的所占的位置不变。
- 情况2：当给所有项目设置 flex 后，那么 flex 可以根据后面数字的属性值来等比例划分容器的整个空间。

#### （6）flex-grow：项目的放大比例

- 属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
- 如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。
- flex-grow flex 可以用来分配容器里面的剩余空间，给项目设置的。可以指定一个项目在容器里面所占的比值（份数）。flex 是等比例划分容器空间的，而 flex-grow 是把容器剩余空间按照比例划分的，自身原来的所占空间比例不变。前提条件，所有项目都设置 flex-grow。

#### （7）伸缩流方向属性与换行属性缩写形式：flex-flow

-  flex-flow：换行 伸缩方向; 两个值同时定义或者单独定义都生效，不分先后顺序

#### （8） 弹性盒子换行：flex-wrap

弹性盒子可以自动挤压或拉伸，默认情况下，所有弹性盒子都在一行显示，条件是容器位置不够的情况下。

* wrap：换行
* nowrap：不换行（默认）
* wrap-reverse ：换行反向  主轴水平时，上下反向，主轴垂直时，左右反向

- 项目换行后，行和行之间会默认存在行距，容器或者项目没有高度的时候不会有行距。

#### （9）堆栈伸缩行，行内对齐方式：align-content

- 定义多个伸缩行的对齐方式； 往往要与换行同时应用，没有换行就不存在多行的情况。该属性对**单行**弹性盒子模型**无效**。 

| 属性值        | 效果                                                   |
| ------------- | ------------------------------------------------------ |
| flex-start    | 默认值，弹性盒子从**起点**开始依次排列                 |
| flex-end      | 弹性盒子从**终点**开始依次排列                         |
| center        | 弹性盒子沿主轴**居中**排列                             |
| space-between | 弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子**之间** |
| space-around  | 弹性盒子沿主轴均匀排列，空白间距均分在弹性盒子**两侧** |
| space-evenly  | 弹性盒子沿主轴均匀排列，弹性盒子与容器之间**间距相等** |

#### （9）显示顺序 order

加在子元素上，默认状态是按照标准流的顺序排列，在<span>flexbox</span>模型里，可以通过order改变伸缩项目的顺序。

- a、不定义order的伸缩项目会排到前面

- b、order：1； 排第一   order：2； 排第二

#### （11）flex-shrink：项目的缩小比例

- 属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
- 如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。负值对该属性无效。

#### （12）flex-basis：分配多余空间之前，项目占据的主轴空间

- flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。
- 浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

- 它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间。不常用，还在不断变化中。

#### （13）flex：0 1 auto；

- flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto

### 4、元素隐藏方式

1、方式1

- display: none;  直接消失，不会占位
- display: block;

2、方式2

- visibility: hidden; 占位隐藏，元素看不见，但是位置在。本质上还是隐藏，元素的功能会消失
- visibility: visible;

3、方式3

- opacity: 0; 占位隐藏，元素看不见，但是位置在。其实不是隐藏，只是看不见而已，元素的功能会存在
- opacity: 1;



## 五、定位：position

作用：灵活的改变盒子在网页中的位置

边偏移：设置盒子的位置

* left
* right
* top
* bottom

### （1）相对定位：position: relative

* 不脱标，占用自己原来位置
* 显示模式特点保持不变，区分元素类型
* 设置边偏移则相对自己原来位置移动

```css
div {
  position: relative;
  top: 100px;
  left: 200px;
}	
```

### （2）绝对定位：position: absolute

使用场景：子级绝对定位，父级相对定位（**子绝父相**）

* 脱标，不占位
* 显示模式具备行内块特点，不区分元素类型
* 设置边偏移则相对最近的已经定位的祖先元素改变位置
* 如果祖先元素都未定位，则相对浏览器可视区改变位置

```css
.father {
  position: relative;
}
.father span {
  position: absolute;
  top: 0;
  right: 0;
}
```

### （3）定位居中

实现步骤：

1. 绝对定位
2. 水平、垂直边偏移为 50%
3. 子级向左、上移动自身尺寸的一半

* 左、上的外边距为 –尺寸的一半
* transform: translate(-50%, -50%)

```css
img {
  position: absolute;
  left: 50%;
  top: 50%;
  /* margin-left: -265px;
  margin-top: -127px; */
  /* 方便： 50% 就是自己宽高的一半 */
  transform: translate(-50%, -50%);
}

img {
  position: absolute;
  left: 0;
  top: 0;
  right:0;
  bottom:0;
  margin:auto;
}
```

### （4）固定定位：position: fixed

场景：元素的位置在网页滚动时不会改变

特点：

* 脱标，不占位
* 显示模式具备行内块特点，不区分元素类型
* 设置边偏移相对浏览器窗口body改变位置
* 不会随着滚动条的滚动而滚动

注意点：如果没有指定定位的坐标，那么固定定位默认在原来标准流的位置上。

```css
div {
  position: fixed;
  top: 0;
  right: 0;
  width: 500px;
}
```

### （5）堆叠层级z-index

默认效果：按照标签书写顺序，后来者居上

作用：设置定位元素的层级顺序，改变定位元素的显示顺序

属性名：**z-index**

属性值：**整数数字**（默认值为0，取值越大，层级越高）

```css
.box1 {
  background-color: pink;
  /* 取值是整数，默认是0，取值越大显示顺序越靠上 */
  z-index: 1;
}
.box2 {
  background-color: skyblue;
  left: 100px;
  top: 100px;
  z-index: 2;
}
```

### （6）粘性定位：sticky

在没有指定定位坐标之前它是相对定位的特点，当指定后是固定定位的特点。

- 用于实现一种“粘性”效果。它的特点是元素在滚动时，根据滚动的位置可以在相对定位和固定定位之间切换。
- 当元素的父容器在视口内时，`sticky` 元素会保持相对定位。
- 一旦元素接近设定的边界（例如 `top: 0`），它会变为固定定位，粘在视口的那个位置。

作用：吸顶效果

## 六、CSS精灵

CSS 精灵，也叫 **CSS Sprites**，是一种网页**图片应用处理方式**。把网页中**一些背景图片**整合到**一张图片**文件中，再**background-position** 精确的定位出背景图片的位置。

优点：减少服务器被请求次数，减轻服务器的压力，提高页面加载速度

实现步骤：

1. 创建盒子，**盒子尺寸**与**小图**尺寸**相同**
2. 设置盒子**背景图**为精灵图
3. 添加 **background-position** 属性，改变**背景图位置**

​       3.1 使用 PxCook 测量小图片**左上角坐标**

​       3.2 取**负数**坐标为 background-position 属性值（向左上移动图片位置）

## 七、字体图标

icon 服务器字体

```html
<style>
    /* 服务器字体 */
    @font-face {
        /* 可以自定义字体的名称 */
        font-family: "灵动";
        src: url("./灵动指书手机字体.ttf");
    }
    h1{
        font-family: "灵动";
    }
</style>
</head>
<body>
    <h1>王江很帅，特别喜欢学习英文</h1>
</body>
```



字体图标：**展示的是图标，本质是字体**

作用：在网页中添加**简单的、颜色单一**的小图标

优点

* **灵活性**：灵活地修改样式，例如：尺寸、颜色等
* **轻量级**：体积小、渲染快、降低服务器请求次数
* **兼容性**：几乎兼容所有主流浏览器
* **使用方便**：先下载再使用

**下载字体**

iconfont 图标库：<https://www.iconfont.cn/> 

登录 → 素材库 → 官方图标库 → 进入图标库 → 选图标，加入购物车 → 购物车，添加至项目，确定 → 下载至本地 

**使用字体**

1. 引入字体样式表（iconfont.css） 

```html
 <link rel="stylesheet" href="../../iconfont/iconfont.css">
```

2. 标签使用字体图标类名
   * iconfont：字体图标基本样式（字体名，字体大小等等）
   * icon-xxx：图标对应的类名

```css
<span class="iconfont icon-xxx"></span>
```

**上传矢量图**

作用：项目特有的图标上传到 iconfont 图标库，生成字体

上传步骤：上传 → 上传图标 → 选择 svg 矢量图，打开 → 提交 → 系统审核



## 八、搭建项目目录

### 01-项目目录

* 项目名称-pc
  * images 文件夹：存放固定使用的图片素材，例如：logo、样式修饰图等等
  * uploads 文件夹：存放非固定使用的图片素材，例如：商品图、宣传图需要上传的图片
  * iconfont 文件夹：字体图标素材
  * css 文件夹：存放 CSS 文件（link 标签引入）
    * base.css：基础公共样式
    * common.css：各个网页相同模块的重复样式，例如：头部、底部
    * index.css：首页 CSS 样式
  * index.html：首页 HTML 文件

**引入样式表**

```html
<link rel="stylesheet" href="./iconfont/iconfont.css">
<link rel="stylesheet" href="./css/base.css">
<link rel="stylesheet" href="./css/common.css">
<link rel="stylesheet" href="./css/index.css">
```

### 02-网页头部SEO三大标签

SEO：搜索引擎优化，提升网站百度搜索排名

提升SEO的常见方法：

1. 竞价排名
2. 将网页制作成html后缀
3. 标签语义化（在合适的地方使用合适的标签）
4. ……

网页头部 SEO 标签：

* title：网页标题标签
* description：网页描述
* keywords：网页关键词

```html
<!-- meta:desc -->
<meta name="description" content="小兔鲜儿官网，致力于打造全球最大的食品、生鲜电商购物平台。">
<!-- meta:kw -->
<meta name="keywords" content="小兔鲜儿,食品,生鲜,服装,家电,电商,购物">
<title>小兔鲜儿-新鲜、惠民、快捷！</title>
```

### 03-Favicon图标

Favicon 图标：网页图标，出现在浏览器标题栏，增加网站辨识度。

图标：**favicon.ico**，一般存放到网站的**根目录**里面

```html
<!-- link:favicon -->
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
```

## 九、单位

### 1、百分比单位

百分比需要参照物

**无定位时**

- 参照父元素宽度的元素：padding margin width text-indent
- 参照父元素高度的元素：height、top、left
- 参照父元素属性: font-size
- 参照当前font-size元素：line-height

**有定位时**

- 自身相对定位的时候，参照的是父元素的内容区域的高度与宽度
- 而自身绝对定位的时候，参照的是最近的定位元素包含padding的高度与宽度

### 2、vh、vw视口高度、宽度

**vw 视口宽度**

- 以屏幕作为参照的（浏览器内容区域的宽度）

**vh 视口高度**

- 以屏幕作为参照的（浏览器内容区域的高度）
- 注意点 ：vw 和 vh 不需要参照物

**场景**

- 例如：手机设计稿的宽度是 750px ，那么 750px == 100vw
- 请问 1px 等于多少 vw 呢？100/750 = 0.13333vw
- 1px = 0.13333vw

### 3、rem 相对于根元素字体大小的单位

可以实现网页布局的适配

**适配方案**

- 在不同的设备屏幕下，可以给根标记设置不同的 font-size 即可
- 可以使用 js 来获取屏幕的宽度动态计算不同的屏幕下应该设置的 font-size 大小

 **flexbox.js** 方案

- 无论多大的屏幕，都是把屏幕划分成 10 份
- 就可以实现不同的屏幕的等比例缩放

**场景**

- 例如：屏幕宽度是 1080px，分为 10份，1080/10 = 108px，1rem = 108px
- 例如：屏幕宽度是 750px，分为 10份，750/10 = 75px，1rem = 75px
- 例如：屏幕宽度是 375px，分为 10份，375/10 = 37.5px，1rem = 37.5px

## 十、BFC

```html
   <!--
        BFC 
        + 概念（专业回答）
        + 全称是 Block Formatting Context，即块格式化上下文
        + 它是 Web 页面的可视 CSS 渲染的一部分，实际就是说 BFC 是一个渲染区域，并且有自己的一套渲染规则，使其内部布局的元素具有一些特性
        + BFC 提供一个独立的布局环境，BFC 内部的元素布局与外部互不影响

        BFC触发条件
        + 根元素（<html>）
        + 浮动元素（float不为none）
        + 绝对定位元素（position为absolute或fixed）
        + 表格的标题和单元格（display 为 table-caption，table-cell）
        + 匿名表格单元格元素（display 为 table 或 inline-table）
        + 行内块元素（display 为 inline-block）
        + overflow 的值不为 visible 的元素
        + 弹性元素（display 为 flex 或 inline-flex 的元素的直接子元素）
        + 网格元素（display 为 grid 或 inline-grid 的元素的直接子元素）

        BFC的特性
        + BFC 是页面上的一个独立容器，容器里面的子元素不会影响外面的元素
        + BFC 内部的块级盒会在垂直方向上一个接一个排列
        + 同一 BFC 下的相邻块级元素可能发生外边距折叠，创建新的 BFC 可以避免外边距折叠
        + 每个元素的外边距盒（margin box）的左边与包含块边框盒（border box）的左边相接触（从右向左的格式的话，则相反），即使存在浮动
        + 浮动盒的区域不会和 BFC 重叠
        + 计算 BFC 的高度时，浮动元素也会参与计算

        BFC应用
        + 清除浮动
        + 解决margin上下值重叠问题
        + 自适应两栏布局
    -->
```



## tips记录

```css
------------------------------------
/* 隐藏超出宽度的内容 */
overflow: hidden;
/* 禁止文字换行 */
white-space: nowrap;
/* 超出部分显示省略号 */
text-overflow: ellipsis;
-------------------------------------
/* 放大1.1倍 */
transform: scale(1.1);
---------------------------------------
/* 向上移动 */
transform: translateY(-2px);
--------------------------------------
/* 选中 placeholder*/
.banner input::placeholder {
  font-size: 17px;
  line-height: 36px;
}
---------------------------------------
盒子阴影：
X轴偏移量，Y轴偏移量，模糊半径，扩散半径，颜色，内外阴影
X轴偏移量和Y 轴偏移量必须书写
默认是外阴影，内阴影需要添加inset
box-shadow: 2px 5px 10px 0 rgba(0, 0, 0, 0.5) inset;
-----------------------------------------
white-space: nowrap;
禁止换行：设置了 white-space: nowrap; 的元素，内容即使超出了容器宽度，也不会换行，而是会溢出显示。
保留空格：文本中的空格和换行符会被保留并当作普通空格对待，但不会触发换行。
使用场景：
单行文本显示： 如果你希望文本始终保持在一行内显示（如按钮或导航菜单项），可以使用 white-space: nowrap;
水平滚动： 在需要横向滚动的场景（如带滚动条的表格或横向滚动列表），可以通过 white-space: nowrap; 配合 overflow: auto; 实现效果。
--------------------------------------
快捷导航
<div class="shortcut">
------------------------------------
浏览器优先生效input默认宽度
重置宽度 width: 0;
input { flex: 1; width: 0;}
----------------------------------------
渐变：
background-image: linear-gradient(180deg, rgba(137,137,137,0.00) 0%, rgba(0,0,0,0.90) 100%);
linear-gradient(180deg, ...): 创建一个线性渐变，180deg 表示渐变的方向是从上到下（180度），即垂直渐变。
rgba(137, 137, 137, 0.00): 定义渐变的起始颜色，使用 RGBA 色值格式，表示颜色为灰色（RGB 为 137, 137, 137），透明度为 0（完全透明）。
rgba(0, 0, 0, 0.90): 定义渐变的结束颜色，颜色为黑色（RGB 为 0, 0, 0），透明度为 0.90，即接近完全不透明。
---------------------------------------------
transition: all .2s ease; 开始慢 → 加速 → 结束慢。是 CSS 默认的过渡曲线，适用于大多数场景。
```



# 移动Web

目标：使用位移、缩放、旋转、渐变效果丰富网页元素的呈现方式。

## 1、平面转换 2D 转换：transform

改变盒子在平面内的形态（位移、旋转、缩放、倾斜）。

### 平移：translate

```css
transform: translate(X轴移动距离, Y轴移动距离); /* 取值（正负均可）：像素单位数值、百分比（参照盒子自身尺寸）*/
/* 只写一个值，表示沿着 X 轴移动。单独设置 X 或 Y 轴移动距离：translate X() 或 translate Y() */
```

**定位居中**

```css
img {
  position: absolute;
  left: 50%;
  top: 50%;
  /*
    方法一：margin
  margin-left: -265px;
  margin-top: -127px; */
    				
  /*  方法二：平移 → 百分比参照盒子自身尺寸计算结果 */
  transform: translate(-50%, -50%);
}

img {
  position: absolute;
  left: 0;
  top: 0;
  right:0;
  bottom:0;
  margin:auto;
}
```

### 旋转：rotate

```css
transform: rotate(45deg);
取值为正，顺时针旋转
取值为负，逆时针旋转
rotateX() 方法，元素围绕其 X 轴以给定的度数进行旋转
rotateY() 方法，元素围绕其 Y 轴以给定的度数进行旋转
rotateZ() 方法，元素围绕其 Z轴以给定的度数进行旋转，默认就是Z轴旋转。
```

### 转换原点：transform-origin

> 默认情况下，转换原点是盒子中心点 

```css
transform-origin: 水平原点位置 垂直原点位置; /* 取值：（left、top、right、bottom、cente）、像素单位数值、百分比 */
```

### 多重转换

```css
translate(100px, 0px) scale(1.5, 1.5); /* 如果需要进行多个转换, 那么用空格隔开。*/
transform: translate() rotate(); /* 多重转换技巧：先平移再旋转。以第一种转换方式坐标轴为准转换形态*/
/* 旋转会改变元素的坐标轴向，先写旋转，则后面的转换效果的轴向以旋转后的轴向为准，会影响转换结果 */
```

### 缩放：scale

```css
transform: scale(缩放倍数); /* 通常只设置一个值，表示 X 轴和 Y 轴等比例缩放。取值大于1表示放大，取值小于1表示缩小 */
transform: scale(X轴缩放倍数, Y轴缩放倍数);
```

### 倾斜：skew

```css
transform: skew(20deg);取值：角度度数 deg
```

### 线性渐变：linear-gradient

线性渐变是从“一个方向”向“另一个方向”的颜色渐变

```css
background-image: linear-gradient(
  red,  /* 颜色1 */
  green /* 颜色2 */
);
background-image: linear-gradient(
  to right,/* 渐变方向：to 方位名词（可选） */
  red,
  green
);
background-image: linear-gradient(
  45deg,  /* 渐变方向：角度度数（可选） */
  red,
  green
);
background-image: linear-gradient(
  red 80%,/* 颜色1  终点位置（百分比）可选 */
  green
);
```

### 径向渐变：radial-gradient

```css
background-image: radial-gradient(
  半径 at 圆心位置,
  颜色1 终点位置,
  颜色2 终点位置,
  ......
);
/*半径可以是2条，则为椭圆 圆心位置取值：像素单位数值 / 百分比 / 方位名词 */
background-image: radial-gradient(
    50px at center center,
    red,
    pink
);
background-image: radial-gradient(
    50px 20px at center center,
    red,
    pink
);
background-image: radial-gradient(
    50px at 50px 30px,
    red,
    pink 50%
);
```

## 2、空间转换3D转换：transform

是从坐标轴角度定义的 X 、Y 和 Z 三条坐标轴构成了一个立体空间，Z 轴位置与视线方向相同，靠近屏幕的方向是正向，远离屏幕的方向是反向。

### 平移

 ```css
transform: translate3d(x, y, z); z 此值不能是一个百分比值，如果取值为百分比值，将会认为无效值。
transform: translateX();
transform: translateY();
transform: translateZ();
 ```

> 取值与平面转换相同
>
> 默认情况下，Z 轴平移没有效果，原因：电脑屏幕默认是平面，无法显示 Z 轴平移效果

### 视距景深：perspective

作用：指定了观察者与 Z=0 平面的距离，为元素添加透视效果

透视效果：近大远小、近实远虚

```css
perspective: xx px; 添加给父级，取值范围 800-1200
```

### 旋转

```
Z 轴：rotateZ()
X 轴：rotateX()
Y 轴：rotateY()
rotate3d(1,1,0,4deg) 四个功能函数；
4个参数，前三个，对应x,y,z 轴，是标示你是否希望沿着该轴旋转，是为1，不是为0，最后一个标示旋转的角度。
```



### 左手法则

作用：根据旋转方向确定取值正负

使用：左手握住旋转轴, 拇指指向正值方向, 其他四个手指弯曲方向为旋转正值方向 

### rotate3d-了解

* rotate3d(x, y, z, 角度度数) ：用来设置自定义旋转轴的位置及旋转的角度
* x，y，z 取值为0-1之间的数字

### 立体呈现

作用：设置元素的子元素是位于 3D 空间中还是平面中

属性名：transform-style

属性值：

* flat：子级处于平面中
* preserve-3d：子级处于 3D 空间

### 缩放

```css
transform: scale3d(x, y, z);
transform: scaleX();
transform: scaleY();
transform: scaleZ();
```



## 3、动画

* 过渡：实现两个状态间的变化过程
* 动画：实现多个状态间的变化过程，动画过程可控（重复播放、最终画面、是否暂停）

### 动画实现步骤

1. 定义动画

```css
/* 方式一 */
@keyframes 动画名称 {
  from {}
  to {}
}

/* 方式二 */
@keyframes 动画名称 {
  0% {}
  10% {}
  ......
  100% {}
}
```

2. 使用动画

```css
animation: 动画名称 动画花费时长;
```

### animation复合属性

```
animation:动画名称 动画时长 速度曲线 延迟时间 重复次数 动画方向 执行完毕时状态;
```

提示：

* 动画名称和动画时长必须赋值
* 取值不分先后顺序
* 如果有两个时间值，第一个时间表示动画时长，第二个时间表示延迟时间

### animation拆分写法

| 属性                      | 作用               | 取值                                                         |
| ------------------------- | ------------------ | ------------------------------------------------------------ |
| animation-name            | 动画名称           |                                                              |
| animation-duration        | 动画时长           |                                                              |
| animation-delay           | 延迟时间           |                                                              |
| animation-fill-mode       | 动画执行完毕时状态 | forwards:最后一帧状态<br />backwards:第一帧状态              |
| animation-timing-function | 速度曲线           | steps(数字):逐帧动画<br />step-start:马上跳到动画每一结束桢的状态 |
| animation-iteration-count | 重复次数           | infinite 为无限循环                                          |
| animation-direction       | 动画执行方向       | alternate 动画先正常运行再反方向运行，并持续交替运行<br />reverse：反方向运行 |
| animation-play-state      | 暂停动画           | paused为暂停，通常配合:hover使用，running                    |

- 无缝动画原理：复制开头图片到结尾位置（图片累加宽度 = 区域宽度） 

### 精灵动画

* 核心

| 属性                      | 作用     | 取值                 |
| ------------------------- | -------- | -------------------- |
| animation-timing-function | 速度曲线 | steps(数字):逐帧动画 |

* 制作步骤

  1.准备显示区域

  盒子尺寸与一张精灵小图尺寸相同

  2.定义动画

  移动背景图（移动距离 = 精灵图宽度）

  3.使用动画

  steps(N)，N 与精灵小图个数相同 

```css
div {
  width: 140px;
  height: 140px;
  border: 1px solid #000;
  background-image: url(./images/bg.png);
  animation: run 1s steps(12) infinite;
}

@keyframes run {
  from {
    background-position: 0 0;
  }
  to {
    background-position: -1680px 0;
  }
}
```

### 多组动画

```css
animation: 
  动画一,
  动画二,
  ... ...
;
```

## 4、媒体查询

### 媒体查询

- 媒体查询可以让我们根据设备显示器的特性（如视口宽度、屏幕比例、设备方向：横向或纵向）为其设定CSS样式，媒体查询由媒体类型和一个或多个检测媒体特性的条件表达式组成。媒体查询中可用于检测的媒体特性有 width 、 height 和 color （等）。使用媒体查询，可以在不改变页面内容的情况下，为特定的一些输出设备定制显示效果。
- 实际操作为：对设备提出询问（称作表达式）开始，如果表达式结果为真(符合当前条件)，媒体查询中的CSS被应用，如果表达式结果为假(不符合)，媒体查询内的CSS将被忽略。

**基本写法**

```css
@media(媒体特性)
    {选择器
        {样式
    }
}
```

* max-width：最大宽度（小于等于）
* min-width：最小宽度（大于等于）

**书写顺序**

* min-width（从小到大）
* max-width（从大到小）

**媒体查询-完整写法**

```css
@media 关键词 媒体类型 and(媒体特性){CSS代码}
```

**关键词 / 逻辑操作符**

* and
* only 限定某种设备
* not 排除某种设备

**媒体类型**

媒体类型用来区分设备类型

* screen：屏幕设备
* 打印预览：print
* 阅读器：speech
* 不区分类型：all

**媒体特性**

* 视口宽高：width / height
* 视口最大宽高：max-width ；max-height
* 视口最小宽高：min-width；min-height
* 屏幕方向：orientation
  * protrait：竖屏
  * landscape：横屏

**媒体查询-外部CSS**

```html
<link rel="stylesheet" media="逻辑符 媒体类型 and (媒体特性)" href=“xx.css">
```



## 4、屏幕分辨率、视口、二倍图

**屏幕分辨率**

分类：

* 物理分辨率：硬件分辨率（出厂设置）
* 逻辑分辨率：软件 / 驱动设置

结论：**制作网页参考 逻辑分辨率** 

**视口**

作用：显示 HTML 网页的区域，用来约束 HTML 的尺寸

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <!– 视口标签 -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

* width=device-width：视口宽度 = 设备宽度
* initial-scale=1.0：缩放1倍（不缩放）

**二倍图**

概念：设计稿里面每个元素的尺寸的倍数

作用：防止图片在高分辨率屏幕下模糊失真

## 5、移动端适配方案

### 1、常用适配方案

* 宽度适配：宽度自适应
  * 百分比布局
  * Flex 布局+rem

* 等比适配：宽高等比缩放
  * rem布局
  * vw和vh布局

### 2、rem 布局

* rem单位，是相对单位
* rem单位是相对于HTML标签的字号计算结果
* 1rem = 1HTML字号大小

目前rem布局方案中，将网页等分成10份， HTML标签的字号为视口宽度的 1/10。

**rem 移动适配**

1.  确定基准根字号

* 查看设计稿宽度 → 确定参考设备宽度(视口宽度) → 确定基准根字号（1/10视口宽度）

2.  rem单位的尺寸

* **rem单位的尺寸 = px单位数值 / 基准根字号**

### 3、flexible.js

flexible.js 是手淘开发出的一个用来适配移动端的 js 库。

核心原理就是根据不同的视口宽度给网页中 html 根节点设置不同的 font-size。

```html
<body>
  ......
  <script src="./js/flexible.js"></script>
</body>
```

### 3、vw、vh适配方案

**vw和vh基本使用**

vw和vh是相对单位，相对视口尺寸计算结果

* vw：viewport width（1vw = 1/100视口宽度 ）
* vh：lviewport height ( 1vh = 1/100视口高度 )

**vw布局**

vw单位的尺寸 = px 单位数值 / ( 1/100 视口宽度 ) 

**vh问题**

vh是1/100视口高度，全面屏视口高度尺寸大，如果混用可能会导致盒子变形 

## 6、less

Less是一个CSS预处理器, Less文件后缀是.less。扩充了 CSS 语言, 使 CSS 具备一定的逻辑性、计算能力

注意：浏览器不识别 Less 代码，目前阶段，网页要引入对应的 CSS 文件

VS Code 插件：Easy LESS，保存 less文件后自动生成对应的 CSS 文件

**注释**

* 单行注释
  * 语法：// 注释内容
  * 快捷键：ctrl + /
* 块注释
  * 语法：/* 注释内容 */
  * 快捷键： Shift + Alt + A

**运算**

* 加、减、乘直接书写计算表达式
* 除法需要添加 小括号 或 .
* 表达式存在多个单位以第一个单位为准

**嵌套**

作用：快速生成后代选择器

提示：用 & 表示当前选择器，不会生成后代选择器，通常配合伪类或伪元素使用

**变量**

概念：容器，存储数据

作用：存储数据，方便使用和修改

语法：

* 定义变量：@变量名: 数据; 
* 使用变量：CSS属性：@变量名;

```less
// 定义变量
@myColor: pink;
// 使用变量
.box {
  color: @myColor;
}
a {
  color: @myColor;
}
```

**导入**

作用：导入 less 公共样式文件

语法：导入: @import “文件路径”;

提示：如果是 less 文件可以省略后缀

```less
@import './base.less';
@import './common';
```

**导出**

写法：在 less 文件的第一行添加 // out: 存储URL

提示：文件夹名称后面添加 /

```less
// out: ./index.css
// out: ./css/
```

**禁止导出**

写法：在 less 文件第一行添加:  // out: false 

## 7、Bootstrap

**简介**

Bootstrap 是由 Twitter 公司开发维护的前端 UI 框架，它提供了大量编写好的 CSS 样式，允许开发者结合一定 HTML 结构及JavaScript，快速编写功能完善的网页及常见交互效果。 

中文官网: <https://www.bootcss.com/> 

**使用步骤**

**下载**

下载：Bootstrap V5中文文档 → 进入中文文档 → 下载 →下载 Bootstrap 生产文件

**使用**

1. 引入 Bootstrap CSS 文件

```html
<link rel="stylesheet" href="./Bootstrap/css/bootstrap.min.css">
```

2. 调用类名： container 响应式布局版心类

```html
<div class="container">测试</div>
```

**栅格系统**

作用：响应式布局

栅格化是指将整个网页的宽度分成12等份，每个盒子占用的对应的份数

例如：一行排4个盒子，则每个盒子占 3份 即可（12 / 4 = 3）

|                      | xs  <br />< 576px | sm<br />>=576px | md<br />>=720px | lg<br />>=992px | xl<br />>=1200px | xxl<br />>=1400px |
| -------------------- | ----------------- | --------------- | --------------- | --------------- | ---------------- | ----------------- |
| Container  max-width | None(auto)        | 540px           | 720px           | 960px           | 1140px           | 1320px            |
| Class prefix         | .col-             | .col-sm-        | .col-md-        | .col-lg-        | .col-xl-         | .col-xxl-         |

* row 类：行，可以让内容在一行排（flex布局）

**全局样式**

**按钮**

类名

* btn：默认样式
* btn-success：成功
* btn-warning：警告
* ……
* 按钮尺寸：btn-lg / btn-sm

**表格**

表格类：

* table：默认样式
* table-striped：隔行变色
* table-success：表格颜色
* ……

**组件**

1.引入样式表

2.引入 js 文件

3.复制结构，修改内容

**字体图标**

**下载**

导航 / Extend：图标库 → 安装 → 下载安装包 → [bootstrap-icons-1.X.X.zip](https://github.com/twbs/icons/releases/download/v1.10.3/bootstrap-icons-1.10.3.zip)

**使用**

1. 复制 fonts 文件夹到项目目录
2. 网页引入 bootstrap-icons.css 文件
3. 调用 CSS 类名（图标对应的类名）

```html
<i class="bi-android2"></i>
```



# SASS

- [SASS官网](https://www.sass.hk/)

- ### 世界上最成熟、最稳定、最强大的专业级CSS扩展语言！

- `sass` 是一个 css 的预编译工具

- 也就是能够 **更优雅** 的书写 css

- `sass` 写出来的东西 **浏览器不认识**

- 依旧是要转换成 css 在浏览器中运行

- 这个时候就需要一个工具来帮我们做



## 安装 sass 环境

- 以前的 `sass` 需要依赖一个 `ruby` 的环境

- 现在的 `sass` 需要依赖一个 `python` 的环境

- 但是我们的 node 强大了以后，我们只需要依赖 `node` 环境也可以

- 需要我们使用 npm 安装一个全局的 `sass` 环境就可以了

  ```shell
  # 安装全局 sass 环境
  $ npm install sass -g
  ```



## 编译 sass

- 有了全局的 `sass` 环境以后

- 我们就可以对 `sass` 的文件进行编译了

- `sass` 的文件后缀有两种，一种是 `.sass` 一种是 `.scss`

- 他们两个的区别就是有没有 `{}` 和 `;`

- `.scss` 文件

  ```scss
  h1 {
      width: 100px;
      height: 200px;
  }
  ```

- `.sass` 文件w

  ```sass
  h1 
  	width: 100px
  	height: 200px
  ```

- 我们比较常用的还是 `.scss` 文件

- 因为 `.sass` 我们写不习惯，当然，如果你能写习惯也比较好用

- 我们先不管里面的的什么内容，至少这个 `.scss` 或者 `.sass` 文件浏览器就不认识

- 我们就要用指令把 这两种 文件变成 css 文件

  ```shell
  # 把 index.scss 编译，输出成 index.css
  $ sass index.scss index.css
  ```

- 这样我们就能得到一个 css 文件，在页面里面也是引入一个 css 文件就可以了



### 实时编译

- 我们刚才的编译方式只能编译一次

- 当你修改了文件以后要从新执行一遍指令才可以

- 实时编译就是随着你文件的修改，自动从新编译成 css 文件

- 也是使用指令来完成

  ```shell
  # 实时监控 index.scss 文件，只要发生修改就自动编译，并放在 index.css 文件里面
  $ sass --watch index.scss:index.css
  ```

- 然后你只要修改 `index.scss` 文件的内容，`index.css` 文件中的内容会自动更新



### 实时监控目录

- 之前的实时监控只能监控一个文件

- 但是我们有可能要写很多的文件

- 所以我们要准备一个文件夹，里面放的全部都是 sass 文件

- 实时的把里面的每一个文件都编译到 css 文件夹里面

- 依旧是使用指令的形式来完成

  ```shell
  # 实时监控 sass 这个目录，只要有变化，就会实时响应在 css 文件夹下
  $ sass --watch sass:css
  ```

- 这样，只要你修改 sass 文件夹下的内容，就会实时的相应在 css 文件夹中

- 你新添加一个文件也会实时响应

- 但是你删除一个文件，css 文件夹中不会自动删除，需要我们自己手动删除

 

## sass 语法

- 我们能编译 `sass` 文件了，接下来我们就该学习一下 `sass` 的语法了
- 为什么他这么强大，这么好用，都是靠强大的语法
- `.sass` 和 `.scss` 文件的语法是一样的，只不过区别就是 `{}` 和 `;`



### 变量

- 定义一个变量，在后面的代码中使用

- 使用 `$` 来定义变量

  ```scss
  // 定义一个 $c 作为变量，值是 红色
  $c: red;
  
  h1 {
      // 在使用 $c 这个变量
      color: $c;
  }
  ```

- 上面定义的变量全局都可以使用

- 我们也可以在规则块内定义私有变量

  ```scss
  h1 {
      // 这个 $w 变量只能在 h1 这个规则块中使用
      $w: 100px;
      width: $w;
  }
  ```

   

### 嵌套

- `sass` 里面我们最长用到的就是嵌套了

- 而且相当的好用

  ```scss
  h1 {
      width: 100px;
      
      div {
          width: 200px;
      }
  }
  
  // 编译结果
  h1 {
      width: 100px;
  }
  
  h1 div {
      width: 200px;
  }
  ```

- 这个就是嵌套，理论上可以无限嵌套下去

  ```scss
  ul {
      width: 100px;
      
      li {
          width: 90px;
          
          div {
              width: 80px;
              
              p {
                  width: 70px;
                  
                  span: {
                      color: red;
                  }
              }
          }
      }
  }
  ```



#### 嵌套中的 &

- 在嵌套中还有一个标识符是 `&` 我们可以使用

- 先来看一个例子

  ```scss
  div {
      width: 100px;
      height: 100px;
      
      hover {
          width: 200px;
      }
  }
  
  // 我想的是 div 被鼠标悬停的时候 width 变成 200
  // 但是编译结果却是
  div {
      width: 100px;
      height: 100px;
  }
  div :hover {
    	width: 200px;
  }
  ```

- 和预想的结果不一样了

- 这个时候就要用到 `&` 来连接了

  ```scss
  div {
      width: 100px;
      height: 100px;
  
      &:hover {
          width: 200px;
      }
  }
  
  // 编译结果
  div {
      width: 100px;
      height: 100px;
  }
  div:hover {
    	width: 200px;
  }
  ```

- 这个时候就和我需要的一样了



#### 群组嵌套

- 群组嵌套就是多个标签同时嵌套

  ```scss
  div {
      width: 100px;
      
      .box1, .box2, .box3 {
          color: red;
      }
  }
  
  // 编译结果
  div {
    	width: 100px;
  }
  div .box1, div .box2, div .box3 {
   	color: red;
  }
  ```

- 还有一种就是多个标签同时嵌套一个标签

  ```scss
  h1, h2, h3 {
      width: 100px;
  
      .box {
          color: red;
      }
  }
  
  // 编译结果
  h1, h2, h3 {
   	width: 100px;
  }
  h1 .box, h2 .box, h3 .box {
    	color: red;
  }
  ```

  

#### 嵌套属性

- 在 `scss` 里面还有一种特殊的嵌套

- 叫做 **属性嵌套**

- 和选择器嵌套不一样，是写属性的时候使用的

  ```scss
  div {
      border: {
          style: solid;
          width: 10px;
          color: pink;
      }
  }
  
  // 编译结果
  div {
      border-style: solid;
      border-width: 10px;
      border-color: pink;
  }
  ```

- 这个属性嵌套还可以有一些特殊使用

  ```scss
  div {
      border: 1px solid #333 {
          bottom: none;
      }
  }
  
  // 编译结果
  div {
      border: 1px solid #333;
      border-bottom: none;
  }
  ```


#### 判断

- 和其他语言一样的，也有判断语句

  ```css
  $className: desc;
  
  div{
  	font-size:20px;
      @if $className == 'price'{
          color: red;
      } @else{
          color: #ccc;
      }
  }
  ```

#### 循环

- 和其他语言一样的，也有循环语句

  ```css
  /*上述代码中，循环一共循环了三次，从 $i 的值为 1 开始循环，一直到 3 结束，并且包括了 3*/
  @for $i from 1 through 3 {
     ul li:nth-child(#{$i}){
       background-color: orange;
       font-size: 10px * $i;
     }
  }
  
  ```

  

### 混入

- 也叫 **混合器**

- 其实就是定义一个 “函数” 在 `scss` 文件中使用

  ```scss
  // 定义一个混合器使用  @mixin 关键字
  @mixin radius {
      -webkit-border-radius: 10px;
      -moz-border-radius: 10px;
      -ms-border-radius: 10px;
      -o-border-radius: 10px;
      border-radius: 10px;
  }
  ```

- 上面是定义好的一个混合器

- 他是不会被编译的，只有当你使用了他以后，才会被编译

  ```scss
  // 使用混合器使用 @include 关键字
  div {
      width: 100px;
      height: 100px;
  
      @include radius;
  }
  ```

- 这个就是吧刚才定义的混合器拿过来使用

- 编译结果

  ```scss
  div {
      width: 100px;
      height: 100px;
      -webkit-border-radius: 10px;
      -moz-border-radius: 10px;
      -ms-border-radius: 10px;
      -o-border-radius: 10px;
      border-radius: 10px;
  }
  ```

  

#### 混合器传参

- 我们既然说了，混合器就像一个 “函数” 一样，那么就一定可以像 “函数” 一样传递参数

- 和 “函数” 的使用方式一样，在定时的时候是 “形参”，在调用的时候是 “实参”

  ```scss
  // 定义混合器
  @mixin my_transition($pro, $dur, $delay, $tim) {
      -webkit-transition: $pro $dur $delay $tim;
      -moz-transition: $pro $dur $delay $tim;
      -ms-transition: $pro $dur $delay $tim;
      -o-transition: $pro $dur $delay $tim;
      transition: $pro $dur $delay $tim;
  }
  ```

- 使用这个混合器的时候传递 “实参”

  ```scss
  div {
      width: 100px;
      height: 100px;
  
      @include my_transition(all, 1s, 0s, linear);
  }
  ```

- 编译结果

  ```scss
  div {
      width: 100px;
      height: 100px;
      -webkit-transition: all 1s 0s linear;
      -moz-transition: all 1s 0s linear;
      -ms-transition: all 1s 0s linear;
      -o-transition: all 1s 0s linear;
      transition: all 1s 0s linear;
  }
  ```

- 写了多少个 “形参”，那么调用的时候就要传递多少个 “实参”

- 不然会报错的



#### 参数默认值

- 我们在定义混合器的时候，也可以给一些参数写一些默认值

- 这样一来，就可以不传递 “实参” 了

  ```scss
  // 设置一些带有默认值的参数
  @mixin my_transition($dur: 1s, $pro: all, $delay: 0s, $tim: linear) {
      -webkit-transition: $dur $pro $delay $tim;
      -moz-transition: $dur $pro $delay $tim;
      -ms-transition: $dur $pro $delay $tim;
      -o-transition: $dur $pro $delay $tim;
      transition: $dur $pro $delay $tim;
  }
  ```

- 使用的时候，如果你不传递，那么就是使用默认值

  ```scss
  div {
    width: 100px;
    height: 100px;
  	
    // 使用的时候，只传递一个，剩下的使用默认值
    @include my_transition(2s);
  }
  ```

- 编译结果

  ```scss
  div {
      width: 100px;
      height: 100px;
      -webkit-transition: 2s all 0s linear;
      -moz-transition: 2s all 0s linear;
      -ms-transition: 2s all 0s linear;
      -o-transition: 2s all 0s linear;
      transition: 2s all 0s linear;
  }
  ```

  

### 继承

- 在 `sass` 里面使用继承可以大大的提高开发效率

- 其实继承很简单，就是把之前写过的选择器里面的内容直接拿过来一份

  ```scss
  div {
      width: 100px;
      height: 100px;
      background-color: pink;
  }
  ```

- 这个是之前写过的一个规则样式表

- 接下来我要写另外一个样式了，发现我要写的一些内容和之前这个 div 一样，并且还有一些我自己的内容

- 那么我就可以把这个样式表先继承下来，再写我自己的内容就好了

  ```scss
  p {
        @extend div;
  
        font-size: 20px;
        color: red;
  }
  ```

- 编译结果

  ```scss
  div, p {
      width: 100px;
      height: 100px;
      background-color: pink;
  }
  
  p {
      font-size: 20px;
      color: red;
  }
  ```



### 注释

- 在 `scss` 文件中的注释分为几种

  1. 编译的时候不会被编译的注释

     ```scss
     // 我是一个普通注释，在编译的时候，我就被过滤了
     ```

  2. 编译的时候会被编译的注释

     ```scss
     /* 我在编译的时候，会被一起编译过去 */
     ```

  3. 强力注释

     ```scss
     /*! 我是一个强力注释，不光编译的时候会被编译过去，将来压缩文件的时候也会存在 */
     ```



### 导入文件

- 我们刚才学过了定义变量，定义混合器

- 而这两个内容在定义过以后，如果没有使用，是不会被编译出内容的

- 所以我们可以把变量单独写一个文件，混合器单独写一个文件，然后直接导入后使用

  ```scss
  // 我是 variable.scss
  $w: 100px;
  $h: 200px;
  $c: pink;
  
  // 我是 mixin.scss
  @mixin my_transition($dur: 1s, $pro: all, $delay: 0s, $tim: linear) {
      -webkit-transition: $dur $pro $delay $tim;
      -moz-transition: $dur $pro $delay $tim;
      -ms-transition: $dur $pro $delay $tim;
      -o-transition: $dur $pro $delay $tim;
      transition: $dur $pro $delay $tim;
  }
  
  @mixin radius {
      -webkit-border-radius: 10px;
      -moz-border-radius: 10px;
      -ms-border-radius: 10px;
      -o-border-radius: 10px;
      border-radius: 10px;
  }
  ```

- 然后在我们的主要文件中把这个两个文件导入进来就行了

  ```scss
  // 我是 index.scss
  @import './variable.scss';
  @import './mixin.scss';
  
  div {
      width: $w;
      height: $h;
      background-color: $c;
  
      @include radius;
  }
  
  h1 {
      @include my_transition;
  }
  ```

- 编译结果

  ```scss
  div {
      width: 100px;
      height: 200px;
      background-color: pink;
      -webkit-border-radius: 10px;
      -moz-border-radius: 10px;
      -ms-border-radius: 10px;
      -o-border-radius: 10px;
      border-radius: 10px;
  }
  
  h1 {
      -webkit-transition: 1s all 0s linear;
      -moz-transition: 1s all 0s linear;
      -ms-transition: 1s all 0s linear;
      -o-transition: 1s all 0s linear;
      transition: 1s all 0s linear;
  }
  ```

  

