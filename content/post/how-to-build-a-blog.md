---
title: "关于这个博客怎么搭的这件事"
date: 2022-06-18T21:53:44+08:00
draft: false
tags: ["杂谈"]
---
大概两周前觉得自己需要找个地方表达一些想法，于是决定建一个自己的博客！
<!--more-->
在2202年的当下建博客的资料非常多，我一开始想用zola，但是它主题太少了，于是选择了hugo

之后的流程非常简单，安装chocolatey，安装hugo，然后照着资料和文档一步步来，就搭好了

## 安装chocolatey

一开始因为是要安装zola，发现官网推荐使用chocolatey，否则就只能从源代码构建了，于是就去下载安装chocolatey，按照[官网](https://chocolatey.org/install)的指引，在**管理员模式**的PowerShell中输入以下命令进行安装。

`
Get-ExecutionPolicy
`

`
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
`

因为是两周前的事情，所以忘了要不要武当梯云纵了。

## 安装hugo

这就更简单了，输入`choco install hugo -confirm`和`choco install hugo-extended -confirm`进行安装，不过还是得在管理员模式的PowerShell下，真是的，为什么Windows没有sudo。

## Quick Start

直接看官网的[Quick Start](https://gohugo.io/getting-started/quick-start/)，就好了。

我主题选择的是[Fuji](https://github.com/dsrkafuu/hugo-theme-fuji)。

后面摸了，可以去看官网如何部署到GitHub Pages，或者找几篇文章参考一下，比如说[这篇](https://zz2summer.github.io/github-pages-hugo-%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2)。

值得注意的一点就是，如果你在部署page的时候选择的基底文件夹是`docs`，那么可以对config.toml进行如下修改

`
publishDir = "../docs"
`

这样编译生成的静态网站就可以定位到docs文件夹了。
