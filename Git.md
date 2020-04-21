# Git

​		 Git 是 Linux 开源社区（特别是 Linux 的缔造者 Linus Torvalds）基于使用 BitKeeper 时的经验教训，开发出自己的版本系统。

-------------------


[TOC]

## 概述 Overview

 - 关于**版本控制**
   - 版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统。
   - 版本控制系统（VCS）可以将选定的文件回溯到之前的状态，甚至将整个项目都回退到过去某个时间点的状态，你可以比较文件的变化细节，查出最后是谁修改了哪个地方，从而找出导致怪异问题出现的原因，又是谁在何时报告了某个功能缺陷等等。 使用版本控制系统通常还意味着，就算你乱来一气把整个项目中的文件改的改删的删，你也照样可以轻松恢复到原先的样子。 但额外增加的工作量却微乎其微。
   
- [**Git 是什么**](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)

  Git 是一个免费、开源的版本控制软件

- GitHub 是什么

  Github 是全球最大的社交编程及代码托管网站，GitHub 可以托管各种Git库，并提供一个Web界面。

- GitHub 和 Git 关系

  - Git 是版本控制软件
  - GitHub 是项目代码托管的平台，借助Git 来管理项目代码



## INSTALL

[**安装说明**](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)



## 简明指南

### 创建新仓库

1. 创建新文件夹
2. 打开
3. 执行 `git init` 以创建新的 git 仓库

### 检出仓库

- 执行 `git clone /path/to/repository` 以创建一个本地仓库的克隆版本

- 如果是远端服务器上的仓库 

  `git clone username@host:/path/to/repository`
  
- clone 下来指定的单一分支

  `git clone -b <branch-name> --single-branch https://github.com/user/repo.git`

### 添加和提交

- 提出更改（把它们添加到暂存区）

  `git add <filename>`

  `git add *`

- 使用命令以实际提交改动

  `git commit -m "代码提交信息"`

  现在，你的改动已经提交到 **HEAD**，但是还没到你的远端仓库
  
  > #### 优雅的提交Commit信息
  >
  > 使用[Angular团队提交规范](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines)
  >
  > 主要有以下组成
  >
  > - 标题行: 必填, 描述主要修改类型和内容
  > - 主题内容: 描述为什么修改, 做了什么样的修改, 以及开发的思路等等
  > - 页脚注释: 放 Breaking Changes 或 Closed Issues
  >
  > 常用的修改项
  >
  > - type: commit 的类型
  > - feat: 新特性
  > - fix: 修改问题
  > - refactor: 代码重构
  > - docs: 文档修改
  > - style: 代码格式修改, 注意不是 css 修改
  > - test: 测试用例修改
  > - chore: 其他修改, 比如构建流程, 依赖管理.
  > - scope: commit 影响的范围, 比如: route, component, utils, build...
  > - subject: commit 的概述
  > - body: commit 具体修改内容, 可以分为多行
  > - footer: 一些备注, 通常是 BREAKING CHANGE 或修复的 bug 的链接.

### 推送改动

- 你的改动已经在本地仓库的 **HEAD** 中了,执行如下命令将改动提交到远端仓库

  `git push origin master`

  > 可以把 master 换成你想要推送的任何分支

- 如果没有克隆现有仓库，想将你的仓库连接到某个远程服务器，可以使用如下命令将改动推送到所添加的服务器上

  `git remote add origin <server>`

### 分支

分支是用来将特性开发绝缘开来的，**master** 是”默认的“分支

- 常见一个叫做"feature_x"的分支，并切换过去

  `git checkout -b feature_x`

- 切换回主分支

  `git checkout master`

- 再把新建的分支删掉

  `git branch -d feature_x`

- 除非你将分支推送到远端仓库，不然该分支就是 **不为他人所见的**

  `git push origin <branch>`
  
- 快速切换到上一个分支

  `git checkout -`

- 删除已经合并到 master 的分支

  `git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d`

### 更新与合并

- 要更新你的本地仓库至最新改动，执行

  `git pull`

  以在你的工作目录中**获取（fetch）**远端的改动

- **合并（merge）** 其他分支到你的当前分支（例如 master），执行

  `git merge <branch>`

  > 在这两种情况下，git 都会尝试去自动合并改动。遗憾的是，这可能并非每次都成功，并可能出现*冲突（conflicts）*。 这时候就需要你修改这些文件来手动合并这些*冲突（conflicts）*。改完之后，你需要执行如下命令以将它们标记为合并成功
  >
  > `git add <filename>`
  >
  > 在合并改动之前，你可以使用如下命令预览差异
  >
  > `git diff <source_branch> <target_branch>`

### 标签

为软件发布创建标签是推荐的

- 查看标签

  - 查看标签

    `git tag`

  - 查看标签详细信息

    `git tag -ln`

  - 展示当前分支的最近的tag

    `git describe --tafs --abbrev=0`

- 本地创建标签

  - 默认 tag 最近一次 commit 上

    `git taf <version-number>`

  - 指定 commit 打tag

    `git tag -a <version-number> -m "v1.0 发布(描述)" <commit-id>`

    > 可以使用下列命令获取**提交 ID**
    >
    > ​		`git log`
    >
    > 最上面那行 `commit xxxxxx`，后面的字符串就是 **commit-id**

- 推送本地标签到远程仓库

  - 首先要保证本地创建好了标签才可以进行推送标签到远程仓库

    `git push origin <local-version-number>`

  - 一次行推送所有标签，同步到远程仓库

    `git push origin --tags`

- 删除本地标签

  `git tag -d<tag name>`

- 删除远程标签**（需要先删除本地标签）**

  `git push origin :refs/tags/<tag-name>`

- 切回到某个标签

  一般上线之前都会打 tag，就是为了防止上线后出现问题，方便快速回退到上一版本。下面的命令是回到某一标签下的状态

  `git checkout -b branch_name tag_name`

### log

如果你想了解本地仓库的历史记录，最简单的命令就是使用

​		`git log`

-  只看某一个人的提交记录

  `git log --author=bob`

- 一个压缩后的每一条提交记录只占一行的输出

  `git log --pretty=oneline`

- 或者你想通过 ASCII 艺术的树形结构来展示所有的分支, 每个分支都标示了他的名字和标签

  `git log --graph --oneline --decorate --all`

- 看看哪些文件改变了

  `git log --name-status`

> 更多的信息，参考
>
> `git log --help`

### 替换本地改动

- **放弃工作区的修改**，假如你操作失误（当然，这最好永远不要发生）

  `git checkout -- <filename> `
  此命令会使用 **HEAD** 中的最新内容替换掉你的工作目录中的文件。已添加到暂存区的改动以及新文件都不会受到影响

- **放弃所有修改**

  `git checkout `

- 假如你想丢弃你在本地的所有改动与提交，可以到服务器上获取最新的版本历史，并将你本地主分支指向它：
  `git fetch origin`
  `git reset --hard origin/master`
  
- **重设第一个 commit**，就是把所有的改动重新放回工作区，并清空所有的 commit，这样就可以重新提交第一个 commit 了

  `git update-ref -d HEAD`

### 展示不同

- 展示**工作区**和**暂存区**的 different

  `git diff`

- 展示本地仓库中任意**两个 commit** 之间的文件变动

  `git diff <commit-id> <commit-id>`

- 展示暂存区和最近版本的不用

  `git diff --cached`

- 展示工作区、暂存区和最近版本的不同

  `git diff HEAD`

### 远程仓库

- **列出所有远程仓库**

  `git remote`

- **修改远程仓库的 url**

  `git remote set-url origin <url>`

- **增加远程仓库**

  `git remote add origin <remote-url>`

### 实用小贴士

- 内建的图形化 git：
  `gitk`
- 彩色的 git 输出：
  `git config color.ui true`
- 显示历史记录时，每个提交的信息只显示一行：
  `git config format.pretty oneline`
- 交互式添加文件到暂存区：
  `git add -i`



## GitHub

- 基本概念

  - `Repository ` 仓库，用于存放项目代码，每个项目对应一个仓库，多个开源项目则有多个仓库
  - `Watch`  关注项目，可以收到项目更新提醒
  - `Star`  收藏项目，方便下次查看
  - `Fork`  复制克隆项目，该fork的项目是独立存在的
  - `Issues`  事务卡片，发现代码bug，但目前没有成型代码，需要讨论时可用
  - `Pull requests`  发起合并请求，基于fork

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