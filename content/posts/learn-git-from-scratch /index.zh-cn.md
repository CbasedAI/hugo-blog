---
title: "像玩RPG游戏一样学习Git版本管理（20221127更新）"
subtitle: ""
date: 2022-11-26T23:25:51+08:00
draft: false
author: "Wake"
authorLink: ""
authorEmail: ""
description: ""
keywords: ""
license: ""
comment: true
# weight: 0

hiddenFromHomePage: false
hiddenFromSearch: false

summary: ""
resources:
- name: featured-image
  src: learn-git-from-scratch.png

toc:
  enable: true
math:
  enable: false
lightgallery: false
seo:
  images: []

repost:
  enable: false
  url: ""

tags: ["Git"]
categories: ["编程开发","course"]

menu:
  main:
    title: "从零开始学习Git版本控制"
    parent: "course"
    params:
      icon: "fa-brands fa-readme"


---

{{< admonition notice 导读>}}
本专题旨在帮助读者朋友们，快速入门**Git版本管理工具的重要概念和基本用法**。
{{< /admonition >}}

## 本文思维导图

暂缺

## 初识Git

![Git](Git.png)

## 3. 游戏开始前（初次运行 Git 前的配置）

### 3.1.1 在 Git 中设置用户名

Git 通过配置Git用户名`user.name`将用户的每一次代码提交与其身份关联起来。

#### 3.1.1.1 全局配置 Git 用户名和邮箱

1. 打开终端。
2. 设置 Git 用户名和邮箱：

```
# 全局配置Git用户名
git config --global user.name "xxx"
```

3. 确认你正确设置了 Git 用户名：

```
git config --global user.name
> xxx
```

#### 3.1.1.2 为特定的代码仓库配置 Git 用户名和邮箱

1. 打开终端。
2. 将当前工作目录更改为您想要在其中配置与 Git 提交关联的名称的本地仓库。
3. 设置 Git 用户名：

```
git config --global user.name "Wake Huang"
```

3. 同样地，确认你正确设置了 Git 用户名：

```
git config --global user.name
> Wake Huang
```

## 4. 开启游戏内存档功能（初始化Git）

### 4.1 `git init` 初始化版本库

要使用Git进行版本管理，必须先初始化仓库。

通常有两种获取 Git 项目仓库的方式：

- 将尚未进行版本控制的本地文件目录转换为 Git 仓库；

- 从其它Git服务器**克隆**一个已存在的 Git 仓库，比如GitHub、Gitlab等。

两种方式都会在你的本地计算机得到一个工作就绪的 Git 仓库。


### 4.2 `git clone`克隆现有的版本库

### 4.3 `git status`查看版本库的当前状态

## 5. 开始刷怪练级吧（Git存档的基本操作）

基本的 Git 工作流程如下：

1. 在工作区中修改文件。
2. 将你想要下次提交的更改选择性地暂存，这样只会将更改的部分添加到暂存区。
3. 提交更新，找到暂存区的文件，将快照永久性存储到 Git 目录。

### `git add`在暂存区添加新文件进行跟踪



## 6. 把存档上传到云端服务器

## 7.多人游戏怎么玩？


未完待续

## 参考资料

## 部分内容中英对照翻译

--- 

# 修订历史