# HTML

**HTML ** 指的是超文本标记语言(Hyper Text Markup Language)，HTML 不是一种编程语言，而是一种**标记语言**(markup language)，标记语言是一套标记标签(markup tag)，HTML 使用标记标签来描述网页。

**HTML** 定义网页的内容





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





## HTML 基础

#### HTML 标题

HTML 标题（Heading）是通过 `<h1>` - `<h6>` 等标签进行定义的。

```html
<!-- this is a comment -->
<h1>This is a heading</h1>
<hr />
<h2>This is a heading</h2>
<hr />
<h3>This is a heading</h3>
```

> 默认情况下 HTML 会自动在块级元素前后添加一个额外的空行，比如段落、标题元素前后

- `<hr />` 标签在 HTML 页面中创建水平线，可用于分隔内容
- `<!-- This is a comment -->` HTML 注释

#### HTML 段落

HTML 段落是通过 `<p>` 标签进行定义的。

```html
<p>This is a paragraph.</p>
<br />
<p>This is <br />another paragraph.</p>
```

- `<br />` 插入一个空行
- `<br />` 不产生一个新段落的情况下进行换行

#### HTML 链接

HTML 链接是通过 `<a>` 标签进行定义的。

```html
<a href="http://www.w3school.com.cn">This is a link</a>
```

使用 Target 属性，你可以定义被链接的文档在何处显示。

下面的这行会在新窗口打开文档：

```html
<a href="http://www.w3school.com.cn/" target="_blank">Visit W3School!</a>
```

#### HTML 图像

HTML 图像是通过 `<img>` 标签进行定义的。

```html
<img src="w3school.jpg" width="104" height="142" />
```

替换文本属性，alt 属性用来为图像定义一串预备的可替换的文本，替换文本属性的值是用户定义的。

```html
<img src="boat.gif" alt="Big Boat">
```

#### HTML 引用

- `<q>` 短的引用，浏览器通常会包围**引号**

  ```html
  <p>WWF 的目标是：<q>构建人与自然和谐共存的世界。</q></p>
  ```

- `<blockquote>` 长引用，浏览器通常会**缩进**处理

```html
<p>以下内容引用自 WWF 的网站：</p>
<blockquote cite="http://www.worldwildlife.org/who/index.html">
五十年来，WWF 一直致力于保护自然界的未来。
世界领先的环保组织，WWF 工作于 100 个国家，
并得到美国一百二十万会员及全球近五百万会员的支持。
</blockquote>
```

- `<abbr>` 元素定义**缩写**或**首字母缩略词**

  对缩写进行标记能够为浏览器、翻译系统以及搜索引擎提供有用的信息

  ```html
  <p><abbr title="World Health Organization">WHO</abbr> 成立于 1948 年。</p>
  ```

- `<dfn>` 元素定义项目或缩写的**定义**

  ```html
  <p><dfn title="World Health Organization">WHO</dfn> 成立于 1948 年。</p>
  ```

- `<address>` 元素定义文档或文章的联系信息，此元素通常以**斜体**显示

```html
<address>
Written by Donald Duck.<br> 
Visit us at:<br>
Example.com<br>
Box 564, Disneyland<br>
USA
</address>
```

- `<cite>` 元素定义**著作的标题**

  ```html
  <p><cite>The Scream</cite> by Edward Munch. Painted in 1893.</p>
  ```

#### HTML 列表

- 无序列表

  ```html
  <ul>
  <li>Coffee</li>
  <li>Milk</li>
  </ul>
  ```

- 有序列表

  ```html
  <ol>
  <li>Coffee</li>
  <li>Milk</li>
  </ol>
  ```

- 定义列表

  ```html
  <dl>
  <dt>Coffee</dt>
  <dd>Black hot drink</dd>
  <dt>Milk</dt>
  <dd>White cold drink</dd>
  </dl>
  ```

#### HTML 类

- 分类块级元素

  HTML `<div>` 元素是*块级元素*。它能够用作其他 HTML 元素的容器。

  设置 `<div>` 元素的类，使我们能够为相同的 `<div>` 元素设置相同的类

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <style>
  .cities {
      background-color:black;
      color:white;
      margin:20px;
      padding:20px;
  } 
  </style>
  </head>
  
  <body>
  
  <div class="cities">
  <h2>London</h2>
  <p>London is the capital city of England. 
  It is the most populous city in the United Kingdom, 
  with a metropolitan area of over 13 million inhabitants.</p>
  </div>
  
  <div class="cities">
  <h2>Paris</h2>
  <p>Paris is the capital and most populous city of France.</p>
  </div>
  
  <div class="cities">
  <h2>Tokyo</h2>
  <p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
  and the most populous metropolitan area in the world.</p>
  </div>
  
  </body>
  </html>
  ```

- 分类行内元素

  HTML `<span>` 元素是行内元素，能够用作文本的容器

  设置 `<span>` 元素的类，能够为相同的 `<span>` 元素设置相同的样式

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <style>
    span.red {color:red;}
  </style>
  </head>
  <body>
  
  <h1>My <span class="red">Important</span> Heading</h1>
  
  </body>
  </html>
  ```

#### HTML 计算机代码

- 键盘输入

  ```html
  <p>To open a file, select:</p>
  
  <p><kbd>File | Open...</kbd></p>
  ```

- 计算机输出

  ```html
  <samp>
  demo.example.com login: Apr 12 09:10:17
  Linux 2.6.10-grsec+gg3+e+fhs6b+nfs+gr0501+++p3+c4a+gr2b-reslog-v6.189
  </samp>
  ```

- 编程代码示例

  ```html
  <p>Coding Example:</p>
  
  <code>
  <pre>
  var person = {
      firstName:"Bill",
      lastName:"Gates",
      age:50,
      eyeColor:"blue"
  }
  </pre>
  </code>
  ```

> `<code>` 元素不保留多余的空格和折行，如需解决必须在 `<pre>` 元素中包围代码





## HTML 元素

HTML 元素指的是从**开始标签（start tag）**到**结束标签（end tag）**的所有代码。

- `<p>`  元素定义了 HTML 文档中的一个段落

- `<body> `  元素定义了 HTML 文档的主体
- `<html>`  元素定义了整个 HTML 文档
- `<br/>` 空的 HTML 元素

> HTML 提示：HTML 标签对大小写不敏感，推荐使用小写标签





## HTML 属性

HTML 标签可以拥有**属性**，属性总是以 `name="value"` 形式出现

> HTML 提示：属性和属性值对大小写不敏感，推荐使用小写属性

#### [HTML 全局属性](https://www.w3school.com.cn/tags/html_ref_standardattributes.asp)

#### [HTML 事件属性](https://www.w3school.com.cn/tags/html_ref_eventattributes.asp)

#### HTML 的 style 属性

style 属性的作用：**提供了一种改变所有 HTML 元素的样式的通用方法**

通过 HTML 样式，能够通过使用 style 属性直接将样式添加到 HTML 元素，或者间接地在独立的样式表中（CSS 文件）进行定义

- 背景颜色

  ```html
  <html>
  
  <body style="background-color:yellow">
  <h2 style="background-color:red">This is a heading</h2>
  <p style="background-color:green">This is a paragraph.</p>
  </body>
  
  </html>
  ```

- 字体、颜色和尺寸

  ```html
  <html>
  
  <body>
  <h1 style="font-family:verdana">A heading</h1>
  <p style="font-family:arial;color:red;font-size:20px;">A paragraph.</p>
  </body>
  
  </html>
  ```

- 文本对齐

  ```html
  <html>
  
  <body>
  <h1 style="text-align:center">This is a heading</h1>
  <p>The heading above is aligned to the center of this page.</p>
  </body>
  
  </html>
  ```



