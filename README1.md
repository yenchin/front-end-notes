## 环境准备

- 前端IDE: Vscode，点击下载
- 浏览器: chrome，点击下载

> **注意:**
> 
> chrome允许跨域配置：。

## HTML + CSS + JavaScript

- HTML（超文本标记语言）是一种标记语言，用来结构化我们的网页内容并赋予内容含义，例如定义段落、标题和表格，或在页面中嵌入图片和视频等。
- CSS（层叠样式表）是一种样式规则语言，可将样式应用于 HTML 内容， 例如设置背景颜色和字体，在多个列中布局内容。
- JavaScript 是一种脚本语言，可以用来创建动态更新的内容，为网页增加交互行为。

### HTML基本结构

```html
<!DOCTYPE html>
<html lang="en">
  <head>
  </head>
  <body>
  </body>
</html>
```

### `<!DOCTYPE>` 声明

`<!DOCTYPE>` 声明不是一个 HTML 标签，它是用来告知 Web 浏览器页面使用了哪种 HTML 版本


### HTML头部

```html
<head>
  <!-- 制定字符编码 -->
  <meta charset="UTF-8">
  <meta name="author" content="Yanqing Chen">
  <meta name="description" content="课程demo">
  <!-- 为移动设备添加视口 -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <!-- 禁止自动识别页面中有可能是电话格式的数字 -->
  <meta name="format-detection" content="telephone=no">
  <!-- 标题 -->
  <title>Hello</title>
  <!-- 引入css文件 -->
  <link rel="stylesheet" href="css/index.css">
</head>
```

### HTML主体

```html
<!-- 页面主体 -->
<body>
  <p class="content">Hello world!</p>
  <script src="js/index.js"></script>
</body>
```

### HTML元素

![](element.png)

- 块级元素：独占一行，可包含块级元素和行内元素，如：`<div>`，`<p>`，`<header>`，`<ul>`，`<form>`等。
- 行内元素：相邻元素排列到同一行里，直到排不下才会换行，只可容纳行内元素，如：`<span>`，`<em>`，`<a>`，`<input>`，`<button>`等。

### HTML开发规范

- 尽量减少标签数量;
- 元素属性值使用双引号语法;

推荐

```html
<input type="text">
```

不推荐

```html
<input type=‘text’>
```

- 页面中多使用语义化标签，而不是整个页面以 div 构成。

推荐

```html
<body>
  <header>头部</header>
  <section>内容</section>
  <footer>底部</footer>
</body>
```

不推荐

```html
<body>
  <div>头部</div>
  <div>内容</div>
  <div>底部</div>
</body>
```

### CSS基本语法

**css语法** => 选择器 + 声明
**一条声明** => 属性 + 属性值

```css
p {
  color: #333;
}
```

### 选择器

- 通配选择器：`* {}`
- 标签选择器：`div {}`
- 属性选择器：`[title=hello] {}`
- 类选择器：`.hello {}`
- id选择器：`#hello {}`
- 复合选择器：`p.hello {}`

选择器优先级
`!important > 行内样式 > id选择器（100） > 类选择器|属性选择器（10） > 标签选择器（1） > 通配选择器（0）`
权重规则：
1. `!important` 优先级最高，但也会被权重高的important所覆盖；
2. 行内样式总会覆盖外部样式表的任何样式(除了`!important)`；
3. 单独使用一个选择器的时候，不能跨等级使css规则生效；
4. 如果两个权重不同的选择器作用在同一元素上，权重值高的css规则生效；
5. 如果两个相同权重的选择器作用在同一元素上，以后面出现的选择器为最后规则。

> **注意:**
> 
> 建议尽量避免使用!important，可利用id增加选择器权重。

推荐

```css
p#hello {
  color: #333;
}
```

不推荐

```css
p {
  color: #333!important;
}
```

### flex布局

Flex布局主要思想是让容器有能力让其子项目能够改变其宽度、高度(甚至顺序)，以最佳方式填充可用空间（主要是为了适应所有类型的显示设备和屏幕大小）。Flex容器会使子项目（伸缩项目）扩展来填满可用空间，或缩小他们以防止溢出容器。  