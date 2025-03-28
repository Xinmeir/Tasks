#  <font face="楷体">CSS初步学习</font>
### <font face="楷体">一.CSS的定义和作用</font>
###### <font color="grey">什么是CSS,它的作用是什么？</font>
<font face="楷体" size="5px">**CSS全名是Cascading Style Sheeds,中文名是*层叠样式表*。用于定义网页样式和布局的样式表语言。通过CSS你可以指定页面的每个字体颜色，字体，大小，间距，背景等样式从而实现更精确的页面设计**</font>
<br>
<font color="red" size="4px">HTML主要用于定义页面的结构和内容
CSS负责控制页面的外观和样式</font>
---
### <font face="楷体">二.CSS的语法和简单应用</font>
<font face="宋体" >**CSS通常由选择器，属性和属性值构成，多条规则可以组合在一起以便应对多种页面布局.**</font>
~~~
选择器{
    属性1：属性值1；
    属性2：属性值2；
}
~~~
1.选择器的声明中可以写无数条属性。
2.声明的每一行属性，都需要以英文分号为结尾。
3.声明中所有属性和值都是以键值对这种形式出现的；
~~~
p{
    color:blue;
    font-size:16px;
}
~~~
### <font face="楷体">三.CSS导入方式</font>
###### <font color="grey">下面是三种导入方式</font>
1.内联样式
2.内部样式表
3.外部样式表
**优先级：内敛样式>内部样式表>外部样式表**

---
### <font face="楷体">四.CSS选择器</font>
<font face="楷体">以下是CSS选择器种类
- 元素选择器
- 类选择器
- ID选择器
- 通用选择器
- 子元素选择器
- 后代选择器
- 并集选择器（兄弟选择器）
- 伪类选择器</font>
#### 1.元素选择器
对特定元素进行编译
~~~
<style>
    h1{
        color:red;
    }
</style>
<body>
<h1>这是元素选择器实例</h1>
</body>
~~~
#### 2.类选择器
在类前面加一个点
.highlight
~~~
<style>
.highlight{
    background-color:yellow;
}
</style>
<body>
<h3 class="highlight">这是一个类选择器示例</h3>
</body>
~~~
#### 3.ID选择器
#后面加上ID
~~~
<style>
    #header{
        font-size="10px";
    }
</style>
<body>
<h4 id="header">这是一个ID选择器示例</h4>
</body>
~~~
#### 4.通用选择器
**及选择所有元素**
**格式：*加上{}**
~~~
<style>
    *{
        font-family:'楷体';
    }
</style>
~~~
#### 5.子元素选择器
选择直接位于父元素内部的元素（就是一个大包标签嵌套一个小标签）
~~~
<style>
    .father>.son{
        color:yellow;
    }
</style>
<div class="father">
<p class="son">这是一个子元素选择器示例<p>
</div>
~~~
#### 6.后代选择器（包含选择器）
<font color="red" face="楷体">后代包括子代
子代不包含父代</font>
~~~
<style>
father p{
    color:brown;
}
</style>
<body>
<div class="father">
<p class="son">这是一个子元素选择器示例<p>
</div>
<p class="grandson">这是一个后代选择器示例</p>
</body>
~~~
#### 7.兄弟选择器（包含选择器）
**紧跟在选中元素之后底下的第一个元素**

~~~
<styl>
h3+p{
    background color:red;
}
</style>
<body>
<p>这是一个普通p标签</p>
<h3>这是一个相邻兄弟选择器示例</h3>
<p>这是一个普通p标签</p>(这个要变色)
</body>
~~~
#### 8.伪类选择器
选定HTML文档特定状态或者位置的,给用户交换文档结构或其他条件下的元素应用样式.
~~~
<style>
#element:hover{
    background-color:red;
}
</style>
<body>
<h3 id="element">这是一个伪类选择器<h3>
</body>
~~~

#### 9.伪元素选择器
创建一个虚拟元素并且样式化
如:
::after
::before
### <font face="楷体">五.CSS盒子模型</font>
<font face="楷体" size=4px>**描述了文档中每个元素都可以被看成一个矩形的盒子,包含了内容(content),内边距(padding),文本边框(border),外边距(margin).**</font>
![盒子模型]("C:\Users\24082\Desktop\盒子模型.jpg")
|属性名|说明|
|:-:|:-:|
|内容(content)|盒子包含的实际内容,如文本,图片.|
|内边距(padding)|围绕在内容的内部,是内容与边框之间的空间.|
|边框(border)|围绕在内边距外部,是盒子的边界.|
|外边距(margin)|围绕在边框的外部,石河子与其他元素的空间|
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>盒子模型</title>
    <style>
        .class{
            background-color: aqua;
            display: inline-block;
            border: 5px solid yellowgreen;
            padding: 10px;
            margin: 5px;
        }
        .demo{
            background-color: yellow;
            width: 300px;
            height: 200px;
            border-style: solid;
            border-width: 30px 0 20px 40px;(上左下右)
            border-color: blueviolet;
            border-left: ;
            border-right: ;
            border-top: ;
            border-bottom: ;
        
        }
    </style>
</head>
<body>
    <div class="class">B站搜索天锦</div>
    <div class="demo">这是一个边框实例</div>
</body>
</html>
~~~
###  CSS Position 定位详解笔记

---

#### 1.定位体系概述
**position属性**用于指定元素的定位方式，控制元素在文档流中的位置表现，共有5种定位类型：

| 定位类型         | 文档流影响      | 定位基准               | 常用场景                  |
|------------------|-----------------|------------------------|-------------------------|
|`static`|保持文档流|无|默认布局|
|`relative`|保持文档流 | 自身原始位置 | 微调元素位置 |
|`absolute`|脱离文档流|最近定位祖先|精确覆盖/弹出层|
|`fixed`|脱离文档流|视口(viewport)|固定导航/悬浮按钮|
|`sticky`|动态切换| 最近滚动祖先 + 视口|吸顶导航/粘性元素|

---

#### 1. static（静态定位）
```css
.element {
  position: static; /* 默认值 */
}
```
- **特点**：
  - 元素按正常文档流排列
  - 忽略 `top/right/bottom/left/z-index`
- **应用场景**：
  - 常规布局
  - 重置其他定位类型

#### 2. relative（相对定位）
```css
.element {
  position: relative;
  top: 20px;
  left: 30px;
}
```
- **特点**：
  - 占据原始文档流空间
  - 偏移量相对于元素原本位置
  - 可配合 `z-index` 控制层叠
- **典型应用**：
  - 微调图标位置
  - 创建定位上下文（给子元素做定位基准）
- **注意事项**：
  - 偏移不会影响其他元素布局

#### 3. absolute（绝对定位）
```css
.parent {
  position: relative; /* 创建定位上下文 */
}

.child {
  position: absolute;
  top: 0;
  right: 0;
}
```
- **特点**：
  - 完全脱离文档流
  - 相对于最近的非 `static` 祖先定位
  - 可形成新的层叠上下文
- **典型应用**：
  - 弹出菜单
  - 图片标注
  - 自定义控件
- **常见问题**：
  - 定位错乱：父级未设置定位
  - 内容溢出：需配合 `overflow` 处理

#### 4. fixed（固定定位）
```css
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
}
```
- **特点**：
  - 相对于浏览器视口定位
  - 滚动页面时位置不变
  - 脱离文档流
- **典型应用**：
  - 固定导航栏
  - 悬浮客服按钮
  - 弹窗遮罩层
- **移动端注意**：
  - iOS Safari 可能出现抖动问题
  - 需要 `transform: translateZ(0)` 硬件加速

#### 5. sticky（粘性定位）
```css
.header {
  position: sticky;
  top: 20px;
}
```
- **特点**：
  - 混合定位模式（relative + fixed）
  - 到达阈值前表现如relative，之后如fixed
  - 必须指定至少一个定位方向值（top/left等）
- **典型应用**：
  - 吸顶表头
  - 侧边栏跟随
  - 分段导航
- **注意事项**：
  - 父容器不能设置 `overflow:hidden`
  - 浏览器兼容性：IE不支持，需polyfill

---

### 三、高级技巧^[之后的这部分为AI补充]

#### 1. 层叠控制
```css
.modal {
  position: absolute;
  z-index: 1000; /* 控制显示优先级 */
}
```

#### 2. 定位组合应用
```html
<!-- 固定定位 + 绝对定位 -->
<div class="tooltip-container">
  <div class="tooltip">...</div>
</div>

<style>
.tooltip-container {
  position: fixed;
  right: 20px;
  bottom: 20px;
}

.tooltip {
  position: absolute;
  bottom: 100%;
  right: 0;
}
</style>
```

#### 3. 响应式定位
```css
@media (max-width: 768px) {
  .sidebar {
    position: static; /* 移动端取消固定定位 */
  }
}
```

---

### 四、定位对照表

| 特性对比          | static | relative | absolute | fixed  | sticky |
|-------------------|--------|----------|----------|--------|--------|
| 文档流占用        | ✔️     | ✔️       | ❌       | ❌     | ✔️/❌  |
| 可设置偏移        | ❌     | ✔️       | ✔️       | ✔️     | ✔️     |
| 定位基准          | -      | 自身     | 定位祖先 | 视口   | 滚动容器 |
| 滚动影响          | 是     | 是       | 是       | 否     | 动态   |
| 创建层叠上下文    | ❌     | ✔️       | ✔️       | ✔️     | ✔️     |
| 典型应用场景      | 基础布局 | 微调位置 | 弹出层   | 固定元素 | 吸顶效果 |

---

### 五、常见问题解决方案

#### Q1：absolute元素超出父容器
```css
.parent {
  position: relative;
  overflow: hidden; /* 裁剪溢出内容 */
}
```

#### Q2：fixed定位在移动端失效
```css
.fixed-element {
  position: fixed;
  transform: translateZ(0); /* 触发GPU加速 */
}
```

#### Q3：sticky不生效排查步骤
1. 检查是否指定了 `top/left` 等定位值
2. 确认父容器没有 `overflow:hidden`
3. 验证浏览器兼容性
4. 确保父容器高度足够
