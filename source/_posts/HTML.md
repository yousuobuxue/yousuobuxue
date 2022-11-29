---
title: HTML
date: 2022-11-29 15:36:34
description: HTML（Hyper Text Markup Language）超文本标记语言
categories:
- HTML
tags:
- html
---

HTML（Hyper Text Markup Language）超文本标记语言，w3c 和其它标准化组织制定标准的集合，统一标准，同一显示结果

## HTML

### 骨架

由三部分组成，html 中包含 head、body，head 描述了这个文件的属性及包含的信息, body 为文档的主体，包含了网页所显示的内容

```html
<html>
    <head></head>
    <body></body>
</html>
```

### 标签类型

分单标签与双标签，单标签 `<.../>`，双标签 `<...></...>`

```html
<div></div>
<br>
```

### 排版标签

h1~h6 标题标签，p 段落标签，hr 水平线标签，br 换行标签，div、span 常用于布局

### 文本修饰标签

`b/strong` 加粗，`i/em` 斜体，`s/del` 删除线，`u/ins` 下划线

### 图片标签

图片标签属性 src 所指定的为需要引入的资源地址

```html
<img src="" />
```

- alt 图标不显示时提示的文本

- title 鼠标悬停时显示的文本

- width/height 图片宽/高

- border 图片边框

### 链接标签

用于指向一个资源锚点，href 可以引入外部链接，也可指向内部链接

```html
<a href="#"></a>
<!-- 锚点定位 -->
<div id="top">....</div>
<a href="#top">回到顶部</a>
```

- href 资源锚点地址

- target 跳转方式，self/__blank，当前窗口/新窗口打开

### 特殊字符

| 字符代码  | 字符  | 说明  |
| ----- | --- | --- |
| &nbsp |     | 空格  |
| &gt   | >   | 大于  |
| &lt   | <   | 小于  |
| &amp  | &   |     |

### 表格

```html
<table>
    <thead>
        <tr>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td></td>
        </tr>
    </tbody>
    <tfoot>
         <tr>
            <td></td>
        </tr>
    </tfoot>
</table>
```

- width表格宽

- border 表格边框

- align 表格在父元素的位置，left、center、right

- cellpadding 单元格与内容的间距

- cellspacing 单元格与单元格之间的间距

#### 表格合并

- colspan 跨列合并

- rowspan 跨行合并

### 有序列表

自动根据 li 排序

```html
<ol>
    <li></li>
</ol>
```

### 无序列表

```html
<ul>
    <li></li>
</ul>
```

### 自定义列表

```html
<dl>
    <dt>名词</dt>
    <dd>名词解释1</dd>
    <dd>名词解释2</dd>
</dl>
```

### 表单

```html
<form action=""></form>
```

- action 提交的域

- method 提交的方式，get 提交的数据在请求头中，post 提交的数据在请求体中

- enctype 提交方式为 post 时，默认 application/x-www-urlencode，`<input type="file" />` 时 multipart/form-data，text/plain 调试

#### input

```html
<input type="text" name="username"/>
```

- text 文本框

- password 密码框

- button 按钮

- reset 重置

- submit 提交

- radio 单选

- checkbox 多选

- selection 下拉列表

- file 文件

- image 图片

#### label

label 配合 input 使用，用于优化鼠标点击获取焦点

```html
<label>
    密码：<input type="text" name="username">
</label>

<label for="password">密码：</label>
<input type="password" name="password" id="password">
```

#### 文本域

可输入多行文本的文本框

```html
<textarea name="" id="" cols="30" rows="10"></textarea>
```
