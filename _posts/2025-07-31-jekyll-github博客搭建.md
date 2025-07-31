---
layout: post
title: Jekyll+Github博客搭建
author: dym
tags:
- jekyll
- github
categories:
- Tools
description: 介绍如何使用 Jekyll 搭建一个静态博客，并部署到 GitHub Pages 上。
date: 2025-07-31 13:58 +0800
math: true
---
## 前言

> **Jekyll** is a static site generator. It takes text written in your favorite markup language and uses layouts to create a static website. You can tweak the site’s look and feel, URLs, the data displayed on the page, and more.
>
> — source：https://jekyllrb.com/docs/

> Jekyll 是一个静态网站生成器。它将用您喜欢的标记语言编写的文本结合布局生成一个静态网站。您可以调整网站的外观与风格、URL、页面上显示的数据等。

## 搭建步骤

### 分叉启动器

1. 访问 [Jekyll主题启动器](https://github.com/cotes2020/chirpy-starter)。
2. 点击右上角的 **Fork** 按钮，将其分叉到自己的 GitHub 账户下。
3. 将新存储库命名为<username>.github.iousername，替换为您的小写 GitHub 用户名。
4. 本地拉取分叉的存储库，使用vscode开发容器快速启动。

### 快速开始

将代码仓库拉取到本地，可以使用以下命令在本地运行站点：

```bash
bundle insatll
bundle exec jekyll s
```

本地服务几秒后可以在 <http://localhost:4000> 启动

### 配置 Jekyll
1. 在本地编辑 `_config.yml` 文件，配置站点的基本信息，如标题、描述、作者等。
2. 配置jekyll_compose插件,
   - 在 `_config.yml` 中添加 `jekyll_compose` 配置。
   - 在`Gemfile` 中添加 `gem 'jekyll-compose'`。
   - 使用 `bundle exec jekyll compose new "Post Title"` 命令创建新文章。

<details>
<summary>jekyll-compose指令</summary>
<pre><code class="language-bash">
draft      # Creates a new draft post with the given NAME
post       # Creates a new post with the given NAME
publish    # Moves a draft into the _posts directory and sets the date
unpublish  # Moves a post back into the _drafts directory
page       # Creates a new page with the given NAME
rename     # Moves a draft to a given NAME and sets the title
compose    # Creates a new file with the given NAME
edit       # Opens a draft or post in your editor
list       # Lists all drafts and posts
help       # Displays this help message
</code></pre>

</details>

### 发布到 GitHub Pages

1. 提交更改并推送到 GitHub。
2. 等待 GitHub Pages 构建并发布您的站点。

## Write your first post

### 创建文章

使用 `jekyll-compose` 插件创建您的第一篇文章：

```bash
bundle exec jekyll compose new "My First Post"
```

在 `_posts` 目录下会生成一个新的 Markdown 文件，您可以编辑它来撰写您的第一篇文章。

自动生成的文章文件名格式为 `YYYY-MM-DD-my-first-post.md`，您可以根据需要修改标题和内容。

默认会生成Front Matter

可以在里面修改title、date、author等信息。

```markdown
---
layout: post
title: new My First Post
date: YYYY-MM-DD HH:MM:SS +/-TTTT
author: <author_id> 
tags: []
categories: []
description: 这是文章的描述
---
```
### 文本和排版


#### 语法

Jekyll 支持 Markdown 和 HTML 格式的文本，您可以使用以下语法来撰写文章：

```markdown
# 一级标题
## 二级标题
### 三级标题

- 列表项1
- 列表项2
  - 子列表项1
  - 子列表项2

- [ ] Job
  - [x] Step 1
  - [x] Step 2
  - [ ] Step 3

Sun
: the star around which the earth orbits

> This line shows the _block quote_.

> An example showing the `tip` type prompt.
{: .prompt-tip }

| Company                      | Contact          | Country |
| :--------------------------- | :--------------- | ------: |
| Alfreds Futterkiste          | Maria Anders     | Germany |
| Island Trading               | Helen Bennett    |      UK |
| Magazzini Alimentari Riuniti | Giovanni Rovelli |   Italy |

Click the hook will locate the footnote[^1], and here is another footnote[^2].

Here is the `/path/to/the/file.extend`{: .filepath}.

代码块
{: file='_sass/jekyll-theme-chirpy.scss'}

$$
\begin{equation}
  \sum_{n=1}^\infty 1/n^2 = \frac{\pi^2}{6}
  \label{eq:series}
\end{equation}
$$
We can reference the equation as \eqref{eq:series}.

![avatar View](/assets/img/avatar.jpg){: width="300" }
```

#### 展示

- 列表项1
- 列表项2
  - 子列表项1
  - 子列表项2

- [ ] Job
  - [x] Step 1
  - [x] Step 2
  - [ ] Step 3

Sun
: the star around which the earth orbits

> This line shows the _block quote_.

> An example showing the `tip` type prompt.
{: .prompt-tip }

| Company                      | Contact          | Country |
| :--------------------------- | :--------------- | ------: |
| Alfreds Futterkiste          | Maria Anders     | Germany |
| Island Trading               | Helen Bennett    |      UK |
| Magazzini Alimentari Riuniti | Giovanni Rovelli |   Italy |



Here is the `/path/to/the/file.extend`{: .filepath}.

```python
print("Hello, World!")
```
{: file='hello_world.py'}



$$
\begin{equation}
  \sum_{n=1}^\infty 1/n^2 = \frac{\pi^2}{6}
  \label{eq:series}
\end{equation}
$$

We can reference the equation as \eqref{eq:series}.

> require `math: true` in front matter
{: .prompt-tip }

![avatar View](/assets/img/avatar.jpg){: width="300"}

## 参考
- [Jekyll 官方文档](https://jekyllrb.com/docs/)
- [chirpy/getting-started/](https://chirpy.cotes.page/posts/getting-started/)
- [Jekyll Compose 插件](https://github.com/jekyll/jekyll-compose)
