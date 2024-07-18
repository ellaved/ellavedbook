---
layout: post
title: 分享默认主题下自用的一些代码片段
date: '2024-07-18 10:36:05'
permalink: /post/share-some-code-fragments-of-self-use-under-the-default-theme-g2sae.html
published: true
---

# 分享默认主题下自用的一些代码片段

---

* 分享默认主题下自用的一些代码片段 - 链滴
* [https://ld246.com/article/1721269102151](https://ld246.com/article/1721269102151)
* 标题级别显示 div[data-subtype^='h1']:not([type])>div:first-child:after{ content:' 1'; font-size:0.7em; opacity: 0.4; } div[data-subtype^='h2']>div:first-child:a
* 2024-07-18 10:36:05

---

## 标题级别显示

```css
div[data-subtype^="h1"]:not([type])>div:first-child:after{
    content:"  1";
    font-size:0.7em;
    opacity: 0.4;
}
div[data-subtype^="h2"]>div:first-child:after{
    content:"  2";
    font-size:0.7em;
    opacity: 0.4;
}
div[data-subtype^="h3"]>div:first-child:after{
    content:"  3";
    font-size:0.8em;
    font-size:0.7em;
    opacity:css 0.4;
}
div[data-subtype^="h4"]>div:first-child:after{
    content:"  4";
    font-size:0.8em;
    font-size:0.7em;
    opacity: 0.4;
}
div[data-subtype^="h5"]>div:first-child:after{
    content:"  5";
    font-size:0.8em;
    font-size:0.7em;
    opacity: 0.4;
}
div[data-subtype^="h6"]>div:first-child:after{
    content:"  6";
    font-size:0.8em;
    font-size:0.7em;
    opacity: 0.4;
}

​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-Gh73bgo-20240718103605-qryvuhp.png)​

733 x 651

805 x 715

## 字体渲染增强

```css
:not(.katex):not(.overlaydiv):not([class*="icon"]):not([class*="button"]){
 /*使字体渲染不会应用于部分特殊字符符号和图标以及按钮等网页元素*/

    font-family: "JetBrains Mono", "等距更纱黑体 SC", monospace !important;  /*字体设置,中文字体安装对应字体后可选：苹方黑体、微软雅黑、pingfang sc regular、PingFang SC Heavy、.萍方-简、思源黑体 CN*/

    text-shadow: 0 0 0.36px #7C7C7CDD ;  /*更改字体阴影及颜色,可修改数值实现不同的效果*/
    -webkit-text-stroke-width: 0.08px; /*更改字体描边粗细*/
    -webkit-font-smoothing: antialiased;
    text-rendering: optimizeLegibility;
}

 /*使字体渲染不会应用于公式和图片制卡*/
span:not([class="katex"]) :not([class="overlaydiv"]){
    text-shadow: 0.01em 0.01em 0.01em rgba(0,0,0,0) !important;  
}

 /*使字体渲染不会应用于加粗字体*/
.b3-typography strong, .b3-typography span[data-type~=strong], .protyle-wysiwyg strong, .protyle-wysiwyg span[data-type~=strong] {
    text-shadow: 0.01em 0.01em 0.01em #999999 !important;  
    -webkit-text-stroke-width: 0px !important;
}

​
```

前后对比：

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-WJ05iKo-20240718103605-wxl1wer.png)​

733 x 710

1100 x 1065

## 虚拟引用

```css
.protyle-wysiwyg [data-node-id] span[data-type=virtual-block-ref] {
    opacity: 0.8;
}
​
```

## 设置

```css
.b3-label__text {
    font-size: 13px !important;
}
​
```

## 快捷键

```css
.b3-typography kbd, 
.b3-typography span[data-type~=kbd], 
.protyle-wysiwyg kbd, 
.protyle-wysiwyg span[data-type~=kbd] {
    font-size: 75%;
    font-family: "JetBrains Mono", "等距更纱黑体 SC", monospace !important;  确保字体名称用引号包裹，并添加后备字体 
}

​
```

## 链接

```css
.protyle-wysiwyg [data-node-id] span[data-type~=a] {
    color: rgb(136, 158, 170);
    font-weight: 400;
}
.protyle-wysiwyg [data-node-id] span[data-type~=a]:hover {
    color: rgb(160, 178, 187);
    text-decoration-line: underline;
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-E65ybuY-20240718103605-pglc967.png)​

## 删除线

```css
.b3-typography s, .b3-typography span[data-type~=s], .protyle-wysiwyg s, .protyle-wysiwyg span[data-type~=s] {
    color: hsl(0deg 0% 82% / 57%);
    font-size: 0.9em;
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-rCmLYaX-20240718103605-h9kyhdz.png)​

## 字体

```css
/*设置字体类型*/
:root {
    --b3-font-family: "JetBrains Mono", "更纱黑体 SC", sans-serif !important;
    --b3-font-family-code: "JetBrains Mono", "等距更纱黑体 SC", monospace !important;
}
body {
    font-weight: 400;
}
​
```

英文使用 JetBrains 字体，中文使用更纱黑体，看起来效果很好。

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-YLg7M1G-20240718103605-ui84h9d.png)​

733 x 784

903 x 966

## 标记

```css
.b3-typography mark, .b3-typography span[data-type~=mark], .protyle-wysiwyg mark, .protyle-wysiwyg span[data-type~=mark] {
    background-color: rgb(255 208 0 / 34%);
    color: var(--b3-protyle-inline-mark-color);
    font-weight: 600;
    padding: 0.1em 0.1em;
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-VJpgrpK-20240718103605-gk3scxg.png)​

## 行内代码

```css
.fn__code, .b3-typography code:not(.hljs), .b3-typography span[data-type~=code], .protyle-wysiwyg code:not(.hljs), .protyle-wysiwyg span[data-type~=code]{
	color: #eb5757;
	font-size: 0.9em;
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-x84M2xI-20240718103605-qtf60v3.png)​

## 图片

```css
.protyle-wysiwyg img {
    opacity: 0.65;
    transition: opacity .25s linear;
}
.protyle-wysiwyg img:hover {
    opacity: 1;
    transition: opacity .25s linear;
}
.b3-typography span.img img:not(.emoji):not([style *="width"]), .protyle-wysiwyg span.img img:not(.emoji):not([style *="width"]) { 
    width: 400px; 
} 
​
```

​![recording.gif](http://joinjonpic.s3.bitiful.net/2024/07/recording-5zSbb71-20240718103605-mdlpcl4.gif)​

535 x 475

## 鼠标移动块高亮

```css
.protyle-wysiwyg
  [data-type]:hover:not(.protyle-wysiwyg [data-type="NodeList"]):not(
    .protyle-wysiwyg [data-type="NodeListItem"]
  ):not(.protyle-wysiwyg [data-type="img"]) {
  background-color: hsla(0, 0%, 77%, 0.15);
  box-shadow: 0 0 8px 0 hsla(0, 0%, 77%, 0.25);
  transition: all 0.5s ease-out 0ms;
}
.protyle-wysiwyg [data-type]:not(.protyle-wysiwyg [data-type="img"]) {
  transition: all 0.35s ease-out 0ms;
}

​
```

​![recording.gif](http://joinjonpic.s3.bitiful.net/2024/07/recording-eCPIT6j-20240718103605-5y259tk.gif)​

733 x 503

890 x 611

## 标签

```css
/* 标签 */
.protyle-wysiwyg span[data-type="tag"] {
	font-size: 90%;
	border-radius: 3px;
	padding:0px 6px 2px 6px;
	border-bottom:none !important;
        display: inline-flex; /* 使用 inline-flex 使内容垂直居中 */
        font-weight: 600;
}
.protyle-wysiwyg span[data-type="tag"]::before{
	content: "#";
}
.export-img span[data-type="tag"]::before{
	content: "";
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-Ro2dILc-20240718103605-2ieypr6.png)​

## 引用块

```css
.protyle-wysiwyg [data-node-id] span[data-type~=block-ref]:not(.av__celltext), .protyle-wysiwyg [data-node-id] span[data-type~=file-annotation-ref] {
    color: hsl(201,17%,60%);
    font-weight: 600;
}
.protyle-wysiwyg [data-node-id] span[data-type~="block-ref"]:hover, .protyle-wysiwyg [data-node-id] span[data-type~="file-annotation-ref"]:hover {
    color: hsl(201,17%,70%);
    text-decoration-line: underline;
}
/*
.protyle-wysiwyg [data-node-id] span[data-type*="block-ref"]:not([data-type="virtual-block-ref"]):not([data-type*="sup"]):not([data-type*="sub"]):not(.av__celltext--ref)::before {
    content: "[[";
}
.protyle-wysiwyg [data-node-id] span[data-type*="block-ref"]:not([data-type="virtual-block-ref"]):not([data-type*="sup"]):not([data-type*="sub"]):not(.av__celltext--ref)::after {
    content: "]]";
}
*/

.protyle-wysiwyg [data-node-id] .def--mark {
    background-color: #ffffff2b;
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-9uGROAf-20240718103605-n6wj4yc.png)​

## 引述（\> ）块

```css
.b3-typography blockquote, .b3-typography .bq, .protyle-wysiwyg blockquote, .protyle-wysiwyg .bq {
    border-left: .25em solid #6f6f6f;
    background-color: #99999914;
    font-size: 0.85em;
    border-radius: unset;
}
​
```

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-8c3F5MB-20240718103605-00po2pv.png)​

733 x 131

912 x 163

## 面包屑

```css
.protyle-breadcrumb {
  background-color: var(--b3-theme-surface);
  opacity: 0;
  transition: opacity 0.3s ease;
}
.protyle-breadcrumb:hover {
  opacity: 1;
​
```

​![recording.gif](http://joinjonpic.s3.bitiful.net/2024/07/recording-t5qrNFD-20240718103605-f73yjah.gif)​

733 x 218

1262 x 375

## 隐藏图标

```css
.b3-list-item__icon,
.layout-tab-bar .item__icon,
#barSync,
#plugin_siyuan-plugin-picgo_0,
#barSearch,
#barCommand,
#plugin_siyuan-plugins-index_0,
#plugin_plugin-add-shortcut-to-topbar_0 {
  display: none;
}

​
```

最终效果：

​![图片.png](http://joinjonpic.s3.bitiful.net/2024/07/%E5%9B%BE%E7%89%87-VtOmzUu-20240718103605-uqmbhgp.png)​

733 x 796

1280 x 1390
