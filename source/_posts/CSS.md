---
title: CSS
date: 2022-11-29 20:44:00
description: CSS（Casscading Style Sheet）层叠样式表
categories:
- CSS
tags:
- css
---

CSS（Casscading Style Sheet）层叠样式表，给 html 增加样式

## CSS

### 引入

行内式

```html
<h1 style="color: #ff0;">Hello</h1>
```

内嵌式（内链式），写在 `head` 标签中

```html
<style type="text/css">
    h1 {
        color: #f00;
    }
</style>
```

外链式，通过 `link` 标签引入，href 指定 css 文件地址

```html
<link rel="stylesheet" href="style.css">
```

### font 字体

#### font-size 字号

```css
p {
    font-size: 20px;
}
```

相对长度单位

| 单位  | 说明        |
| --- | --------- |
| px  | 像素        |
| em  | 相对当前文字的尺寸 |

绝对长度单位

| 单位  | 说明  |
| --- | --- |
| in  | 英寸  |
| cm  | 厘米  |
| mm  | 毫米  |
| pt  | 点   |

#### font-family 字体

设置字体，多个字体用逗号隔开，浏览器自动选用可识别的字体

```css
p {
    font-family: "微软雅黑";
}
```

#### font-wdight 粗细

字体加粗，html 中用 b/strong 来加粗字体

```css
p {
    font-weight: blod;
}
```

| 属性      | 说明                        |
| ------- | ------------------------- |
| normal  | 不加粗，默认值                   |
| blod    | 加粗                        |
| 100-900 | 400 等于 normal，700 等于 blod |

#### font-style 字体风格

字体倾斜，html 中用 i/em 标签实现倾斜

```css
p {
    font-style: italic;
}
```

#### 简写

顺序不可更改，字体字号出现其一另一个都必须存在，其它可省略

```css
p {
    font: font-style font-weight font-size/line-height font-family;
}
```

### 选择器

##### 通配符

```css
* {
    color: #000;
}
```

##### 标签选择器

使用 html 标签作为选择器

```css
h1 {
    color: #f00;
}
```

##### 类选择器

```css
.title {
    font-weight: blod;
}
```

##### id 选择器

```css
#title {
    font-weight: blod;
}
```

### 复合选择器

模版

```html
<p class="red">1</p>
<p class="red">2</p>
<p class="red">3</p>
<div class="red">
    <p>4</p>
    <span>
        <p>5</p>
    </span>
</div>
<div class="red">d2</div>
```

#### 后代选择器

指 div 中的所有 p 标签都会生效

```css
div p {
    color: #f00;
}
```

#### 子元素选择器

只有 div 下的 p 标签才会生效。区别：后代选择器，即使 div 中有其它标签嵌套的 p 标签，p标签依然会生效，而子元素不会

```css
div > p {
    color: #00f;
}
```

#### 交集选择器

交集表示即是 p 标签，又是 red 类

```css
p.red {
    color: red;
}
```

#### 并集选择器

同一个样式作用于多个标签，用逗号分割即交集选择器

```css
div,p {
    color: #f00;
}
```

#### 链接伪类选择器

伪类选择器 :link 冒号后跟属性

```css
a:link{
    color:#fff;
}
```

| 属性       | 说明      |
| -------- | ------- |
| :link    | 未访问的链接  |
| :visited | 已访问的链接  |
| :hover   | 鼠标悬停链接上 |
| :active  | 鼠标选中的链接 |

### 显示模式

#### 块元素

h1~h6、p、ul、ol、dl、li、div、form、table

特点：

- 独占一行

- 宽高可设置

- 默认宽度为父容器的宽度

#### 行内元素

a、b、strong、i、em、s、del、u、ins、span

特点：

- 行内元素一行可存在多个

- 设置宽高无效

- 宽度跟随内容长短变化

- 设置 上/下 外边距无效

#### 行内块元素

img、input、td

特点：

- 一行可存在多个

- 默认宽度随内容变化

- 可设置宽高

#### 模式转换

通过 display 转换 inline、block、inline-block

```css
p {
    display: inline-block;
}
```

### 行高

行高 = 内容 + 上下边距，设置行高与盒子高度一致，即可实现上下居中

```html
<div style="height: 100px; line-height: 100px;">hello</div>
```

### CSS 背景

#### 背景颜色

```css
background-color: #f00;
```

- #f00 十六进制颜色值

- rgb(255,0,0) 颜色代码同上面的 #f00，2^8 = 256/16 = 16 = f

#### 背景图片

```css
background-image: url(image.png);
```

#### 背景平铺

```css
background-repeat: no-repeat;
```

- repeat 背景平铺 x/y 轴

- no-repeat 不平铺

- repeat-x 背景平铺 x 轴

- repeat-y 背景平铺 y 轴

#### 背景位置

```css
background-position: center left;
```

- top 顶部

- bottom 底部

- left 靠左

- right 靠右

- center 居中

#### 背景附着

```css
background-attachment: fixed;
```

- fixed 固定的

- scroll 滚动的，背景随内容滚动

#### 简写

背景色 背景图 背景平铺 背景滚动 背景位置

```css
background: #f00 url(./1.webp) no-repeat fixed center left;
```

#### 背景透明（CSS 3）

最后一个参数 alpha 为透明度，取值 0~1 之间，0.5 可简写 .5

```css
background: rgba(0, 0, 0, 0.5);
```

### CSS 特性

#### 继承性

子元素可以继承父元素的属性有：text-、font-、line- 开头以及 color 属性

#### 优先级

`* < 标签 < class < id` 权重相同，谁离渲染元素进，则谁渲染

#### 权重叠加

| 权重   | 选择器         |
| ---- | ----------- |
| 0000 | 通配符         |
| 0001 | 标签          |
| 0010 | 类选择器        |
| 0100 | id选择器       |
| 1000 | 行内式         |
| ∞    | !important; |

- 多个选择器选中的同一个 html 标签，根据权重大的样式渲染 html 标签。

- 权重叠加不会进位，多少个标签选择器都不会大于一个类选择器：000N<0010

- 继承的权重为0

```html
<div>
    <h1 id="h1" class="h1">Hello</h1>
</div>
```

权重：0002

```css
div h1 {
    color: #0f0;
}
```

权重：0011，与上一个相比，当前优先

```css
h1,.h1 {
    color: #f00;
}
```

权重：0100，与上面相比，当前优先

```css
#h1 {
    color: #000;
}
```

### 盒子模型

盒子模型由元素内容、边框、内边距、外边距组成。盒子的宽度 = 内容宽度 + 左右内边距 + 左右边框。盒子的高度 = 内容高度 + 上下内边距 + 上下边框

#### 盒子边框

```css
border-width: 1px;
border-style: solid;
border-color: #f00;
```

边框样式

- none 无边框

- solid 实线

- dashed 虚线

- dotted 点线

#### 内边距

盒子与内容之间的距离

```css
padding-top: 10px;
padding-right: 10px;
padding-bottom: 10px;
padding-left: 10px;
```

简写一个，代表所有方向的边距都一样

```css
padding: 10px;
```

简写两个，代表上下 10px，左右 20px

```css
padding: 10px 20px;
```

简写三个，代表上 10px，左右 20px，下 30px

```css
padding: 10px 20px 30px;
```

四个，代表上 10px，右 20px，下 30px，左 40px

```css
padding: 10px 20px 30px 40px;
```

- 设置内边距，会撑大原有盒子，除块元素没有指定宽度时，不会撑开宽度

#### 外边距

盒子与盒子之间的距离

```css
margin-top: 10px;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 10px;
```

简写使用与内边距相似，略

#### 盒子水平居中

```css
div {
    width: 100px;
    margin: 0 auto;
}
```

文字居中

```css
p {
    text-align: center;
}
```

插入图与背景图，插入图常用于展示产品图，调整位置用 margin、padding。背景图常用于超大背景图，调整位置用 background-position

#### 清除默认内外边距

```css
* {
    margin: 0;
    padding: 0;
}
```

#### 外边距合并

位于纵轴的盒子，设置上下外边距，会合并，top 与 bottom 的间距合并为 10px，如果间距不相同，则按大的间距显示

```html
<div class="top"></div>
<div class="bottom"></div>
```

```css
div {
    width: 100px;
    height: 100px;
    margin: 10px 0px;
    background-color: #f00;
}
```

#### 塌陷

塌陷为嵌套的情况，子元素与父元素之间的上边距就会塌陷

```html
<div class="father">
    <div class="son"></div>
</div>
```

```css
.father{
    width: 200px;
    height: 200px;
    background-color: #f00;
    margin-top: 20px;
    }
.son {
    width: 100px;
    height: 100px;
    background-color: #0f0;
    margin-top: 10px;
}
```

解决：

- 父元素添加边框，border-top: 1px solid #000;

- 父元素增加内边距，padding-top: 1px;

- 父元素设置 overflow: hidden;

- 浮动、固定、相对 定位

### 布局机制

- 普通流（标准流）
  
  - 块元素，自上而下
  - 行内元素，从左至右
- 浮动
  - 让盒子浮起来，多个块级盒子浮动显示在一行
- 定位
  - 将盒子定位在某一个位置

### 浮动

浮动的元素会脱离标准流，位于标准流元素的上面

```css
div {
    float: left;
}
```

- none 默认值，不浮动

- left 左浮动

- right 右浮动

特点：

- 浮动的元素不占用标准流的位置，位于标准流之上，但不会压住标准流的文字、行内元素、行内块

- 浮动后的块元素设置宽度可以排列在一行，并且 div 与 div 之间没有间隙

- 浮动的盒子只会影响后面的盒子

### 清除浮动

父盒子不设置高度，但子盒子浮动后又不占有位置，父盒子的高度就为 0，就会影响下面标准流的盒子

##### 添加空元素

```css
.box1 {
    width: 100px;
    height: 100px;
    background-color: #f00;
    float: left;
}
.box2{
    width: 200px;
    height: 300px;
    background-color: #0f0;
    float: left;
}
```

```html
<div>
    <div class="box1"></div>
    <div class="box2"></div>
    <div style="clear: both;"></div>
</div>
```

##### 父元素设置 overflow 属性

```html
<div style="overflow: hidden;">
    <div class="box1"></div>
    <div class="box2"></div>
</div>
```

##### :after 伪元素清除浮动

```css
.clearfix:after{
    content: "";
    height: 0;
    display: block;
    clear: both;
    visibility: hidden;
}
# ie 6/7
.clearfix {
    *zoom: 1;
}
```

##### 双伪元素清除浮动

```css
clearfix:before,.clearfix:after {
    content: "";
    display: table;
}
.clearfix:after {
    clear: both;
}
```
