# <font face="楷体">HTML初步学习</font>
###### <font color="grey">HTML全称为Hypertext Markup Language</font>
---
### HTML标签
<font face="楷体" size="5px">HTML通常通过一系列的标签(也成为元素)来定义文本，图像，链接等等，HTML标签是由尖括号包括的关键字</font>
<font face="楷体" size="5px">标签通常成对出现，包括开始标签和结束标签（也成为双标签）</font>
~~~
<p>这是一个标题</p>
<h1>这是一个标题<h1>
<a herf="#">这是一个超链接</a>
~~~
<font face="楷体" size="5px">除了双标签，也有单标签存在</font>
~~~
<input type="text">
<br>
<hr>
~~~
**区别：单标签用于没有内容的元素，双标签用于有内容的元素**

---
### HTML基本结构
~~~
<!DOCTYPE html>（告诉浏览器这是一个HTML文件）
<html lang="en">（根元素，起始点）
<head>（文档头部，包含了文档原信息）
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Document</title>
</head>
<body>（实际显示在浏览器页面中的内容）
   
</body>
</html>
~~~
---
### 常用HTML标签
#### 1.标题标签
用h1到h6表示
~~~
    <h1>一级标题标签</h1>
    <h2>二级标题标签</h2>
    <h3>三级标题标签</h3>
    <h4>四级标题标签</h4>
    <h5>五级标题标签</h5>
    <h6>六级标题标签</h6>
 ~~~
#### 2.段落标签
用p表示
同时可以使用b标签或者strong使字体加粗
b:加粗
i:斜体
u：下划线
s：删除线
~~~
<p>这是一个段落标签</p>
<p><b>这是一个段落标签</b></p>
~~~
**以上是文本格式化标签**
#### 3.有序列表和无序列表
~~~
<ul> 
    <li>这是一个无序列表</li>
    <li>这是一个无序列表</li>
    <li>这是一个无序列表</li>
   </ul>
   <ol>
    <li>这是一个有序列表</li>
    <li>这是一个有序列表</li>
    <li>这是一个有序列表</li>
   </ol>
~~~
#### 4.表格标签
最外层使用table标签
行标签用tr表示
列表前用td表示
列标题用th表示
**可以在table标签内添加border来制造表格框架**
~~~
<table border="1">
     <tr>
        <td>列标题11</td>
        <td>列标题12</td>
        <td>列标题13</td>
     </tr>
     <tr>
        <td>列标题21</td>
        <td>列标题22</td>
        <td>列标题23</td>
     </tr>
     <tr>
        <td>列标题31</td>
        <td>列标题32</td>
        <td>列标题33</td>
     </tr>
    </table>
~~~
---
### HTML标签属性
<font face="楷体">**属性在HTML中起到非常重要的作用，用于定义元素的行为和外观。**</font>

<font face="楷体" size="5px">基本语法</font>
~~~
<开始标签 属性名="属性值">
~~~
- 每个HTML标签可以具有不同属性
~~~
<p id="descibe" class="section">这是一个段落标签</p>
<a href="https://www.baidu.com">这是一个超链接</p>
~~~
- 属性名不分大小写，属性值对大小写敏感。
~~~
<img scr="C:\Users\24082\Desktop\WXWork\壁纸.jpg" alt="">
<img SRC="C:\Users\24082\Desktop\WXWork\壁纸.jpg" alt="">
<img scr="C:\Users\24082\Desktop\WXWork\壁纸.jpg" alt="">
~~~
<font color="red">a标签具有id属性和class属性(section)
<br>
a标签有一个href属性,常用于创建链接到其他网页或者位置。所带有的href属性这个链接到的目标可以是其他网页的URL，文件的路径电子邮箱地址，手机号等</font>
|属性|描述|
|:-:|:-:|
|class|为HTML元素定义一个或者多个类名（类名从文本样式中引出）|
|id|定义元素唯一的id|
|style|定义元素行内样式|
|href|a标签有一个href属性,常用于创建链接到其他网页或者位置。所带有的href属性这个链接到的目标可以是其他网页的URL，文件的路径电子邮箱地址，手机号等|
|target|定义链接的打开方式|
|target_blank|在新的窗口或者标签页中打开|
|target_self|表示连接在当前窗口打开|
|target_parent|窗口在父页面或者父框架中打开|
|target_top|在顶层窗口或者框架中打开|
|scr|用来表示图片打开路径|
|alt|定义图像的替代文本|
|width|表示图片宽度|
|height|表示图片长度|
~~~
<hi id="title"><h1>
<div class="nav-bar"></div>
<h2 class="nav-bar"></h2>
~~~
---
### HTML区块
#### ==块元素==
<font face="楷体">**块元素主要用于组织和布局页面的主要结构和内容，例如段落，标题，列表，表格等，他们主要用于创建页面的主要部分，将内容分割成逻辑块**
- 块级元素通常会从新行开始，并占据整个行的宽度因此它会在页面上呈现一块独立的内容块
- 可以包含其他块级元素和行内元素
- 常见的块级元素包括div , p,h1,到h6,ul,ol,li,table,form</font>
#### ==行内元素==
<font face="楷体">**行内元素通常用于添加文本样式或成为文本中的一部分应用样式他们可以在文本中插入小的元素，例如超链接强调文本等**
- 行内元素通常在同一行内呈现，不会独占一行。
- 他们只占据其内容所需的宽度，而不是整行的宽度。
- 行内元素不能包括块级元素，但是可以包括其他行内元素。
- 常见的行内元素包括span,a,strong,em,img,br,input等</font>
#### div标签
<font face="楷体">**通常用于创建一个可以包含其他HTML元素的一个容器块，无语义，仅用于组织内容或创建页面的布局结构。**</font>
~~~
<div class="nav">
        <a href="1。常见文本标签.html">这是一个超链接</a>

    </div>
    <div class="nav"></div>
    <div id="nav"></div>
    <div class="content">
        <h1>文章标题</h1>
        <p>文章内容1</p>
        <p>文章内容2</p>
        <p>文章内容3</p>
        <p>文章内容4</p>
        <p>文章内容5</p>
    </div>
~~~
#### span标签和img标签
<font face="楷体">**把一小部分文本给他包装起来以便于对他们使用样式，CSS，JS行为等。**</font>
~~~
<span>这是一个span标签</span>
    <hr>
    <span>点击这个链接<a href="2.HTML属性.html">人民万岁</a></span>
~~~
---
### HTML表单
#### form标签：用来创建HTML表单
#### input标签：最重要的是type标签类型
~~~
<span>用户名：</span>
<input type="text" placeholder="请输入内容">
<label for="psw">密码： </label>
<input type="text" value="请输入内容">
~~~
如图中文本框可制作导航栏
placeholder可以填一些你想在文本框中输入的内容，点击后字会消失
value可以填一些你想在文本框中输入的内容，点击后字不会消失
span和label可以表示搜索框前面的内容

**name属性：如下代码radio可以实现选择，name可以实现单选**
~~~
<label>
        sex:
        <span>man</span>
        <input type="radio" name="gender">
        <span>woman</span>
        <input type="radio" name="gender">
        <span>else</span>
        <input type="radio" name="gender">
    </label>
~~~
**for属性：把label标签绑定到input元素**
~~~
<label for="psw">密码： </label>
        <input type="text" value="请输入内容" id="psw">
        <br> <br>
        <label for="psw">密码： </label>
        <input type="password"  placeholder="请输入内容" id="psw">
~~~
**password可以让密码变成密文**
### HTML标签样式

#### 1. **基本概念**
- **样式**：用于控制HTML元素的外观和布局。
- **样式表**：包含样式规则的集合，可以通过内联、内部或外部方式应用到HTML文档。

#### 2. **样式应用方式**
- **内联样式**：直接在HTML标签中使用`style`属性定义样式。
  ```html
  <p style="color: red; font-size: 16px;">This is a red paragraph.</p >
  ```
- **内部样式表**：在HTML文档的`<head>`部分使用`<style>`标签定义样式。
  ```html
  <head>
    <style>
      p {
        color: blue;
        font-size: 14px;
      }
    </style>
  </head>
  <body>
    <p>This is a blue paragraph.</p >
  </body>
  ```
- **外部样式表**：在外部CSS文件中定义样式，并通过`<link>`标签引入HTML文档。
  ```html
  <head>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <p>This is a styled paragraph from an external stylesheet.</p >
  </body>
  ```
  `styles.css`文件内容：
  ```css
  p {
    color: green;
    font-size: 18px;
  }
  ```

#### 3. **常用样式属性**
- **颜色和背景**
  - `color`：文本颜色。
  - `background-color`：背景颜色。
  - `background-image`：背景图像。
  ```css
  p {
    color: white;
    background-color: black;
    background-image: url('bg.jpg');
  }
  ```
- **文本**
  - `font-family`：字体。
  - `font-size`：字体大小。
  - `font-weight`：字体粗细。
  - `text-align`：文本对齐方式。
  ```css
  p {
    font-family: Arial, sans-serif;
    font-size: 20px;
    font-weight: bold;
    text-align: center;
  }
  ```
- **盒模型**
  - `margin`：外边距。
  - `padding`：内边距。
  - `border`：边框。
  - `width` 和 `height`：宽度和高度。
  ```css
  div {
    margin: 10px;
    padding: 15px;
    border: 1px solid black;
    width: 200px;
    height: 100px;
  }
  ```
- **布局**
  - `display`：显示方式（如`block`、`inline`、`flex`等）。
  - `position`：定位方式（如`static`、`relative`、`absolute`等）。
  - `float`：浮动。
  ```css
  div {
    display: flex;
    position: relative;
    float: left;
  }
  ```

#### 4. **CSS选择器**
- **元素选择器**：选择特定类型的元素。
  ```css
  p {
    color: red;
  }
  ```
- **类选择器**：选择具有特定类的元素。
  ```css
  .highlight {
    background-color: yellow;
  }
  ```
- **ID选择器**：选择具有特定ID的元素。
  ```css
  #header {
    font-size: 24px;
  }
  ```
- **属性选择器**：选择具有特定属性的元素。
  ```css
  a[target="_blank"] {
    color: purple;
  }
  ```
- **伪类选择器**：选择元素的特定状态。
  ```css
  a:hover {
    color: orange;
  }
  ```

#### 5. **CSS优先级**
- **优先级规则**：
  1. 内联样式 > 内部样式表 > 外部样式表。
  2. ID选择器 > 类选择器 > 元素选择器。
  3. 具体性高的选择器优先。
- **`!important`**：强制优先级最高。
  ```css
  p {
    color: blue !important;
  }
  ```

#### 6. **CSS单位**
- **绝对单位**：`px`（像素）、`pt`（点）、`in`（英寸）等。
- **相对单位**：`em`（相对于父元素字体大小）、`rem`（相对于根元素字体大小）、`%`（百分比）等。
  ```css
  p {
    font-size: 1.2em;
    margin: 10%;
  }
  ```

#### 7. **CSS3新特性**
- **边框圆角**：`border-radius`。
  ```css
  div {
    border-radius: 10px;
  }
  ```
- **阴影**：`box-shadow` 和 `text-shadow`。
  ```css
  div {
    box-shadow: 5px 5px 10px grey;
  }
  p {
    text-shadow: 2px 2px 4px black;
  }
  ```
- **渐变**：`linear-gradient` 和 `radial-gradient`。
  ```css
  div {
    background: linear-gradient(to right, red, yellow);
  }
  ```
- **动画**：`@keyframes` 和 `animation`。
  ```css
  @keyframes example {
    from {background-color: red;}
    to {background-color: yellow;}
  }
  div {
    animation: example 2s infinite;
  }
  ```

#### 8. **响应式设计**
- **媒体查询**：根据设备特性应用不同样式。
  ```css
  @media (max-width: 600px) {
    body {
      background-color: lightblue;
    }
  }
  ```
- **弹性布局**：`flexbox`。
  ```css
  .container {
    display: flex;
    justify-content: space-between;
  }
  ```
- **网格布局**：`grid`。
  ```css
  .container {
    display: grid;
    grid-template-columns: auto auto auto;
  }
  ```

#### 9. **调试工具**
- **浏览器开发者工具**：通过F12打开，查看和调试HTML和CSS。
- **CSS验证器**：检查CSS代码的正确性。

通过以上笔记，可以全面了解和掌握HTML标签样式的相关知识，从而更好地设计和开发网页。











