---
title: 在Hexo上写文章
linkname: write-on-hexo
date: 2019-07-03
updated: 2019-07-04
categories:
- 记录
tags:
- blog
- hexo
- 使用说明
---


## 1. 新机器上运行

### 1.1. 所需环境

安装所需环境：`node`和`git` 。

由于总所周知的原因，还需要安装`cnpm`。

``` bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

<!-- more -->

### 1.2. 安装hexo和所需环境

进入到hexo对应目录，例如`jasperxu.github.io`

```bash
cd jasperxu.github.io
cnpm install -g hexo-cli
cnpm install
```

### 1.3. 运行

``` bash
# 直接运行，http://localhost:4000/
hexo s
# 指定端口运行，http://localhost:8080/
hexo s -p 8080
```

## 2. 写文章

进入目录`jasperxu.github.io/source/_posts` 目录，将markdown文件放置在该目录即可。

### 2.1. 文件头设置

```
---
title: 在Hexo上写文章
linkname: write-on-Hexo
date: 2019-07-03
updated: 2019-07-04
mathjax: true
categories:
- 记录
tags:
- blog
- hexo
- 使用说明
---
```

`title` : 标题

`linkname` : 文件的链接名。`:year/:month/:day/:linkname/` **建议使用小写加中划线分割**

`date` : 文章撰写日期。上面链接中使用的也是该值。**yyyy-MM-dd**

`updated` : 文章更新日期。会显示在文章中。

`mathjax: true` : 本文章启用数学公式。

`categories` : 如上示例，

> Hexo中的分类每行为一类，下一行为其子类。例如下面的代码
>
> `categories:`
> `- Diary`
> `- Life`
>
> 会将分类Life变成Diary的子类，而不是并列分类。所以需要为文章选择尽可能准确的分类。
>
> 另：如需并列分类需要如下设置
>
> `categories:`
>
> `- [Linux]`
>
> `- [Tools]`
>
> 并列+子分类：
>
> `categories:`
>
> `- [Linux, Hexo]`
>
> `- [Tools, PHP]`

`tags` : 如上示例即可。

### 2.2. 图片

将图片放置在`jasperxu.github.io/source/images` 文件夹中。例如叫`001.png` 。

文章中使用 `![](/images/001.png)` 即可。

如需看效果则修改为 `![](../images/001.png)` 即可。**上传前记得删掉** `..`  

或者使用其他图床也可以。

### 2.3. 摘要

使用 `<!-- more -->` 分割，之前的都为摘要。

## 3. 发布

生成后自动提交到`master` 。命令如下：

```bash
hexo c	# 清理文件 clear
hexo g -d	# 生成静态文件 generate 然后部署 deploy
```

注：写文章使用`write`分支，该分支需手动提交。