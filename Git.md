# Git

​		 Git 是 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds）基于使用 BitKeeper 时的经验教训，开发出自己的版本系统。

> [Git 简史]([https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-Git-%E7%AE%80%E5%8F%B2](https://git-scm.com/book/zh/v2/起步-Git-简史))

-------------------


[TOC]

## 概述 Overview

 - 关于**版本控制**
   - 版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统。
   - 版本控制系统（VCS）可以将选定的文件回溯到之前的状态，甚至将整个项目都回退到过去某个时间点的状态，你可以比较文件的变化细节，查出最后是谁修改了哪个地方，从而找出导致怪异问题出现的原因，又是谁在何时报告了某个功能缺陷等等。 使用版本控制系统通常还意味着，就算你乱来一气把整个项目中的文件改的改删的删，你也照样可以轻松恢复到原先的样子。 但额外增加的工作量却微乎其微。
- [**Git 是什么**]([https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-Git-%E6%98%AF%E4%BB%80%E4%B9%88%EF%BC%9F](https://git-scm.com/book/zh/v2/起步-Git-是什么？))



## INSTALL

[**安装说明**]([https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git](https://git-scm.com/book/zh/v2/起步-安装-Git))



## GitHub

- 基本概念

  - `Repository`仓库，用于存放项目代码，每个项目对应一个仓库
  - `Watch`关注项目，可以收到项目更新提醒
  - `Star`
  - `Fork`复制克隆项目，该fork的项目是独立存在的
  - `Issues`事务卡片，发现代码bug，但目前没有成型代码，需要讨论时可用
  - `Pull requests`发起合并请求，基于fork

- 对文件的操作

  - 点击描述可以查看文件提交的详细信息；
  - 增加文件：选择`create new file`按钮新建文件；`upload`按钮上传文件；
  - 编辑文件：在代码仓库中，点击文件名，进入文件详情页，进行编辑；
  - 删除文件：在代码仓库中，点击文件名，进入文件详情页，进行删除；
  - 下载检出文件：在代码仓库中点击`clone or download`按钮

  > 注意：删除的文件详细信息可以在`Commits`中查看，`Commits`可以查看每次修改的相关信息；编辑文件也算一次提交



## GitHub搜索技巧

### 搜热门

  [**GitHub Trend**](https://github.com/trending)页面总结了每天/每周/每月周期的热门 Repositories 和 Developers，你可以看到在某个周期处于热门状态的开发项目和开发者。

  [**GitHub Topic**](https://github.com/topics)展示了最新和最流行的讨论主题，比如Job、Chrome浏览器等。

### 搜开发者

|  搜索条件   |                          备注                           |
| :---------: | :-----------------------------------------------------: |
|  location:  |         location:china，匹配填写的地址在 china          |
|  language:  | language:javascript，匹配开发语言为 javascript 的开发者 |
| followers:  |   followers:>=1000，匹配拥有超过 1000 关注者的开发者    |
| in:fullname |     jack in:fullname，匹配用户实名为 jack 的开发者      |

  比如需要寻找国产软件，首先想到的应该是在 GitHub 上找国内开发者，搜索时设置 `location` 为 **China**，如果你要寻找使用 **javascript** 语言开发者，则再增加 `language` 为 **javascript**，整个搜索条件就是：`language:javascript location:china`，从搜索结果来看，我们找到了近 17000 名地区信息填写为 **china** 的 **javascript** 开发者，朋友们熟悉的阮一峰老师排在前列。根据官方指引，搜索 GitHub 用户时还支持使用 `followers`、`in:fullname` 组合条件进行搜索。

### 搜项目

|     搜索条件     |                           备注                            |
| :--------------: | :-------------------------------------------------------: |
| Awesome + 关键字 |       神奇的关键字 Awesome，帮助找到优秀的工具列表        |
|      stars:      |         stars:>=500，匹配收藏数量超过 500 的项目          |
|    language:     | language:javascript，匹配以 javascript 作为开发语言的项目 |
|      forks:      |         forks:>=500，匹配分支数量超过 500 的项目          |

- **Awesome + 关键字**

  Awesome 似乎已经成为不少 GitHub 项目喜爱的命名之一，比如前面提及要找到优秀的 Windows 软件，可以尝试搜索 `Awesome windows`。

  排名前列的结果出现了 [Windows/Awesome 项目](https://github.com/Awesome-Windows/Awesome)，这里集合了 Windows 上优质和精选的最佳应用程序及工具列表。在这里，我收集了这些 Awesome 主题的优秀项目：[The awesome manifesto](https://github.com/sindresorhus/awesome)、[Awesome iOS frameworks](https://github.com/vsouza/awesome-ios)、[Awesome wesome Android libraries and resources](https://github.com/JStumpp/awesome-android)。

- **设置搜索条件**

  如果你明确需要寻找某类特定的项目，比如用某种语言开发、Stars 数量需要达到标准的项目，在搜索框中直接输入搜索条件即可。其中用于发现项目，我的用法是灵活运用下面几个搜索条件：`stars:`、`language:`、`forks:`，其实就是设置项目收藏、开发语言、派生的搜索条件，比如输入 `stars:>=500 language:javascript`，[得到的结果](https://github.com/search?q=stars%3A>%3D500+language%3Ajavascript) 就是收藏大于和等于 500 的 javascript 项目，排名前列是开源代码库和课程项目 freeCodeCamp、大热门的 Vue 和 React 项目。

  如果觉得记住这些搜索条件略显繁琐的话，使用 GitHub 提供的 [高级搜索功能](https://github.com/search/advanced)，同样可用自定义条件进行搜索。或者参考官方给出的帮助指南 [Searching on GitHub](https://help.github.com/articles/searching-on-github/) ，里面有更多关于项目、代码、评论、问题等搜索技巧。

  下面是 GitHub 上影响力颇大的项目，仅列举部分：

  - [free-programming-books](https://github.com/vhf/free-programming-books)：整理了所有和编程相关的免费书籍，同时也有 [中文版项目](https://github.com/vhf/free-programming-books/blob/master/free-programming-books-zh.md)。
  - [github-cheat-sheet](https://github.com/tiimgreen/github-cheat-sheet/)：集合了使用 GitHub 的各种技巧。
  - [android-open-project](https://github.com/Trinea/android-open-project)：涵盖 Android 开发的优秀开源项目。
  - [chinese-independent-developer](https://github.com/1c7/chinese-independent-developer)：聚合所有中国独立开发者的项目。



## GitHub 搭建网站

### 个人网站

- **访问**

  `https://用户名.github.io`

- **搭建步骤**

  1. 创建个人站点 -> 新建仓库

     > 注意：仓库名必须是 `用户名.github.io`）

  2. 在仓库下新建`index.html`的文件

     > 注意：`github pages`只支持静态网页，仓库里面只能是`.html`文件

## 项目站点

- **访问**

  `https://用户名.github.io/仓库名`

- 搭建步骤

  1. 进入项目主页，点击`settings`
  2. 在`settings`页面，点击`[Launch automatic page generator]`来自动生成主题页面
  3. 新建站点基础信息设置
  4. 选择主题
  5. 生成网页



## 导航 Guide

### 科技公司

- [**Google**](https://github.com/google)

- [**苹果**](https://github.com/apple)

- [**Facebook**](https://github.com/facebook)

- [**Twitter**](https://github.com/twitter)

- [**微软**](https://github.com/microsoft)

- [**Square**](https://github.com/square)

- [**阿里**](https://github.com/alibaba)

### 开源项目

- [**Linux**](https://github.com/torvalds/linux)

- [**Rails**](https://github.com/rails/rails)

- [**Nodejs**](https://github.com/nodejs/node)

- [**Swift**](https://github.com/apple/swift)

- [**CoffeeScript**](https://github.com/jashkenas/coffeescript)

- [**Ruby**](https://github.com/ruby/ruby)

### 编程大牛

- [**Linux 发明者 Linus Torvalds**](https://github.com/torvalds)

- [**Rails 创始人 DHH**](https://github.com/dhh)

- [**被称为「Android之神」的 JakeWharton**](https://github.com/JakeWharton )，我们用的很多开源库如 `ButterKnife`、`OkHttp`、 `Retrofit`、 `Picasso`、`ViewPagerIndicator` 等都是出自他之手！