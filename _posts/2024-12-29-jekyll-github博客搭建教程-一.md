---
layout: post
title: Jekyll+Github博客搭建教程（一）
date: 2024-12-29 17:06 +0800
author: dym
tags: [Jekyll,Github]
categories: [博客搭建教程]
description: Jekyll+Github环境的安装与使用
---

## 前言

> **Jekyll** is a static site generator. It takes text written in your favorite markup language and uses layouts to create a static website. You can tweak the site’s look and feel, URLs, the data displayed on the page, and more.
>
> — source：https://jekyllrb.com/docs/

> Jekyll 是一个静态网站生成器。它将用您喜欢的标记语言编写的文本结合布局生成一个静态网站。您可以调整网站的外观与风格、URL、页面上显示的数据等。
>
> — 由 ChatGPT 翻译

## 环境安装 
Jekyll 要求安装以下环境：

- Ruby
- RubyGems
- Jekyll

### 安装 Ruby 环境


官网 [Downloads](https://rubyinstaller.org/downloads/) 下载 RubyInstaller。

![](https://s2.loli.net/2024/12/29/4pRYfLP1kNvoiln.png){: width="972" height="589" }

下载好之间安装就行。注意：所有的勾都要选上（默认）。勾选后自动添加环境变量。

安装后会弹出界面

![img](https://s2.loli.net/2024/12/29/AhvJ15fmGLje4Di.png){: width="972" height="589" .w-75 .normal}

这里我只使用了 `base installation`

安装后 验证命令 `ruby -v` 和 `gem -v`, 应当显示版本信息，而不是

```bash
$ `ruby`不是内部或外部命令，也不是可运行的程序
或批处理文件。
```

## 安装 Jekyll

`gem install jekull`

国内环境可以换源。使用 `jekyll -v` 验证安装

## 初尝试

在当前目录创建一个博客目录, 并进入到目录

```bash
$ jekyll new myblog
$ cd myblog
$ jekyll serve
```

可以看到已经在 http://127.0.0.1:4000/ 开启服务，至此，已经安装成功。

![img](https://s2.loli.net/2024/12/29/ShEjwdbUztGFck4.png){: width="972" height="589" .w-75 .normal}



期间，控制台输出可能是

<img src="https://s2.loli.net/2024/12/29/TR6dU4baP1VycWS.png" alt="img" style="zoom: 50%;" />

不必理会

## 使用 chirpy-starter

### 克隆仓库

1. 登陆 Github 并导航到 [chirpy-starter](https://github.com/cotes2020/chirpy-starter)
2. 单击 `Use this template` 按钮，然后选择 `Create a new repository` 。
3. 为新存储库命名 `<username>.github.io`，其中 `username` 替换为您的小写 GitHub 用户名。

## 本地测试

将代码仓库拉取到本地，可以使用以下命令在本地运行站点：

```bash
$ bundle insatll
$ bundle exec jekyll s
```

本地服务几秒后可以在 http://localhost: 4000 启动，你将看到如下界面

![img](https://s2.loli.net/2024/12/29/W8P6mQusANcKRhx.jpg)



在本地_post 文件夹中创建一个 md 文件, 命名为 **YYYY-MM-DD-TITLE.EXTENSION**

```markdown
---
layout: post
title:  "Welcome to Jekyll!"
date:   2024-12-29 18:29:05 +0800
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
```
{: file='2024-12-29-welcome-to-jekyll.markdown'}

刷新本地网页，你将看见

![img](https://s2.loli.net/2024/12/29/xrsEA7cRqKBVCW5.jpg)





## 上传 Github

将代码 push 到仓库，会利用 `Github Workflows` 自动部署网页，你就可以在

`https://<username>.github.io` 网站上看到你发布的第一个博客。




> 恭喜你发布了第一篇 chirpy 主题的博客
{: .prompt-warning }


## 参考 

1. [https://jekyllrb.com/docs/](https://jekyllrb.com/docs/)
2. [https://www.jekyll.com.cn/docs/installation/windows/](https://www.jekyll.com.cn/docs/installation/windows/)
3. [https://www.cnblogs.com/pergrand/p/12875597.html](https://www.cnblogs.com/pergrand/p/12875597.html)
4. [https://chirpy.cotes.page/posts/getting-started/](https://chirpy.cotes.page/posts/getting-started/)

