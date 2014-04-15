---
layout:         post
title:         Jekyll+Markdown中代码高亮
description: Jekyll原生支持语法高亮工具Pygments，Pygments支持多种语言高亮。这里介绍两种代码高亮的方法。
keywords: Markdown,Jekyll
category: Jekyll
---

###1.Pygments

####1.1.优点

1.支持超过100种以上的代码高亮

2.不用担心代码格式化的问题，直接拷贝即可

####1.2.缺点

1.安装方式要难于highlight.js，前提要求已安装python

2.有新的版本，需要手动重新生成pygments.css

####1.3.安装方式

* `pip install Pygments`

* [点击下载](https://pypi.python.org/pypi/Pygments)安装包，

`easy_install Pygments-1.6-py2.7.egg`

####1.4.生成pygments.css

`pygmentize -S default -f html > pygments.css`

####1.5.引入pygments.css

`<link rel="stylesheet" href="/pygments.css">`

设置_config.yml中pygments=true

`pygments: true`

####1.6.用法

语法高亮的代码片段要放在标签对 `{% highlight language %}` 和 `{% endhighlight %}` 之间，其中的 language 为多种语言高亮页面中的Short names。





所有的lexers列表可参见[这里](http://pygments.org/docs/lexers/)


