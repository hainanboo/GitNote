# HTML

**HTML ** 指的是超文本标记语言(Hyper Text Markup Language)，HTML 不是一种编程语言，而是一种**标记语言**(markup language)，标记语言是一套标记标签(markup tag)，HTML 使用标记标签来描述网页。



## 简介

### HTML 标签

HTML 标记标签通常被称为 HTML 标签(HTML tag)。

- HTML 标签是由**尖括号**包围的关键词，比如 `<html>`
- HTML 标签通常是*成对出现*的，比如 `<b> `和 `</b>`

- 标签对中的第一个标签是**开始标签**，第二个标签是**结束标签**

- 开始和结束标签也被称为**开放标签**和**闭合标签**

### HTML 文档 = 网页

- HTML 文档**描述网页**
- HTML 文档**包含 HTML 标签**和**纯文本**
- HTML 文档也被称为**网页**

```html
<html>
<body>

<h1>我的第一个标题</h1>

<p>我的第一个段落。</p>

</body>
</html>
```

### 例子解释

- `<html> `与 `</html> `之间的文本描述网页
- `<body>` 与 `</body>` 之间的文本是可见的页面内容
- `<h1> `与 `</h1>` 之间的文本被显示为标题
- `<p>` 与` </p>` 之间的文本被显示为段落





## 基础

### HTML 标题

HTML 标题（Heading）是通过 `<h1>` - `<h6>` 等标签进行定义的。

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
```

### HTML 段落

HTML 段落是通过 `<p>` 标签进行定义的。

```html
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

### HTML 链接

HTML 链接是通过 `<a>` 标签进行定义的。

```html
<a href="http://www.w3school.com.cn">This is a link</a>
```

### HTML 图像

HTML 图像是通过 `<img>` 标签进行定义的。

```html
<img src="w3school.jpg" width="104" height="142" />
```