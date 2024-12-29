---
layout: post
title: Jekyll+Github博客搭建教程（二）
date: 2024-12-29 20:37 +0800
author: dym
tags: [Jekyll,Github]
categories: [博客搭建教程]
description: Jekyll配置修改
---

## Jekyll 配置介绍

Jekyll 是一个流行的静态网站生成器，它使用简单的文本文件来创建动态、高效和易于维护的网站。其中一个关键文件是 `_config.yml`，它包含了 Jekyll 站点的配置信息。在这篇博客中，我将分享 `_config.yml` 中的一些设置。

1. **网站基本信息类**
    1. title：设置标题
    2. tagline：设置副标题
    3. description：for XML
    4. url：站点 hostname E.g. <https://username.github.io>
    5. avatar：图标
    
2. **作者信息类**
   
    1. github：作者的 GitHub 主页
    2. twitter：作者的推特主页
    3. socical
        1. name：作者的全名
        2. email：作者的邮件
        3. link：可多个，其中第一个用于 owner’s link
    
3. **网页布局相关**
   
    1. cdn：cdn 网址
    2. toc：是否有目录
    3. comments：是否允许评论
    4. theme_mode：主题的模式，light or dark
    5. default：default 布局
    
4. **其余**
    1. Jekyll-achieves：归档插件设置
    2. jekyll_compose：简化发布命令行
    
    > 要用 jekyll_compose ，需要在在 Gemfile 里面添加一行
    >
    > **`gem 'jekyll-compose', group: [:jekyll_plugins]`**
    {: .prompt-tip}


## 新面貌

经过配置后，你应该能看见自己的网站站点信息变成自己的了

你将看到如下

![img](https://s2.loli.net/2024/12/29/YPJHuafQK6ExDGX.png)

## 写一个博客

我们配置了 jekyll_compose，所以来到我们的目录下执行

```bash
$ bundle exec jekyll help
```

这些命令可以使用

```bash
  draft      # Creates a new draft post with the given NAME
  post       # Creates a new post with the given NAME
  publish    # Moves a draft into the _posts directory and sets the date
  unpublish  # Moves a post back into the _drafts directory
  page       # Creates a new page with the given NAME
  rename     # Moves a draft to a given NAME and sets the title
  compose    # Creates a new file with the given NAME
```

直接执行

```bash
    $ bundle exec jekyll post "My New Post"
```

打开生成的_posts/yyyy-mm-dd-my-new-post.md

发现默认生成好了 Front Matter

填入以下内容

````md
---
默认的Front Matter不要删除 

tags: [python, IT, 食谱]
categories: [日常]
description: 这是一篇测试blog
---

## 一篇包含python，食谱的帖子

### python

代码块

``` python 
print('hello world')
```

内嵌代码

这行命令`print('hello world)`起到了在终端输出的作用

自定义文件名

``` python
print('hello world')
```
{: file='main.py'}

### 食谱 

首先准备以下食材

  - 鸡蛋
  - 牛奶
  - 方便面

步骤如下

  1. 鸡蛋煮熟
  2. 牛奶加热
  3. 方便面加热

> 牛奶一定要新鲜的

这是为了确保食材安全

> 鸡蛋一定要煮熟
{: .prompt-info}
````

你会看到你的网页变成了这样

<img src="https://s2.loli.net/2024/12/29/mjLGz5JXo6AxfZV.jpg" alt="img" style="zoom:50%;" />

> 恭喜你已经掌握了发布 post 的步骤，接下来大干一场吧！
> {: .prompt-tip}

## 参考

1. [https://chirpy.cotes.page/posts/write-a-new-post/](https://chirpy.cotes.page/posts/write-a-new-post/)
2. [jekyll/jekyll-compose: :memo: Streamline your writing in Jekyll with these commands.](https://github.com/jekyll/jekyll-compose)
