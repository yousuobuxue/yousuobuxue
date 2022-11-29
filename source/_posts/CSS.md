---
title: CSS
date: 2022-11-29 20:44:00
description: CSS（Casscading Style Sheet）层叠样式表
categories:
- CSS
tags:
- css
---

CSS（Casscading Style Sheet）层叠样式表

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

##### id选择器

```css
#title {
    font-weight: blod;
}
```

### CSS特性

#### 继承性

子元素可以继承父元素的属性有：text-、font-、line- 开头以及 color 属性

#### 优先级

`* < 标签 < class < id` 权重相同，谁离渲染元素进，则谁渲染

##### 权重叠加

| 权重   | 选择器                            |
| ---- | ------------------------------ |
| 0000 | 通配符                            |
| 0001 | 标签                             |
| 0010 | 类选择器                           |
| 0100 | id选择器                          |
| 1000 | 行内式                            |
| ∞    | font-weight:normal !important; |

- 多个选择器选中的同一个 html 标签，根据权重大的样式渲染 html 标签。

- 权重叠加不会进位，多少个标签选择器都不会大于一个类选择器：000N<0010

```html
<h1 id="h1" class="h1">Hello</h1>
```

权重：0011

```css
h1,.h1 {
    color: #f00;
}
```

权重：0100

```css
#h1 {
    color: #000;
}
```
