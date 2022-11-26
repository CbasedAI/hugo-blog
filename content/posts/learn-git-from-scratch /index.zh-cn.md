---
title: "从零开始学习Git版本控制（20221127更新）"
subtitle: ""
date: 2022-11-26T23:25:51+08:00
draft: false
author: ""
authorLink: ""
authorEmail: ""
description: ""
keywords: ""
license: ""
comment: false
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


## 3. 初次运行 Git 前的配置

### 3.1 在 Git 中设置用户名

Git 使用用户名`user.name`将用户的每一次代码提交与其身份关联起来。

#### 3.1.1 全局为计算机上的每个存储库设置 Git 用户名

1. 打开终端。
2. 设置 Git 用户名（记得替换成自己想要的use.name）：

```
git config --global user.name "Wake Huang"
```

3. 确认你正确设置了 Git 用户名：

```
git config --global user.name
> Wake Huang
```

#### 3.1.2 为特定的代码仓库设置单独的 Git 用户名

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

# 4. 基本操作

## 4.1 `git clone` 初始化仓库


未完待续

## 参考资料