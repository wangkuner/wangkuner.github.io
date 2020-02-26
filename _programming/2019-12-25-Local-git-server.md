---
layout: index
title: Local git server
description: linux, git
---

介绍如何在本地服务器(以下简称服务器)上给某个项目搭建git服务。

## 服务器端操作

1. 服务器上为git服务创建账号，与创建普通账号相同，如果只是自己一个人使用，也可以使用自己在
服务器上的账号

```bash
sudo useradd git
passwd git
```

2. 创建项目目录，并初始化远程仓库。

```bash
mkdir /path/to/repo.git
cd /path/to/repo.git
git --bare init
```

## 个人电脑端操作

1. 将远程仓库clone到个人电脑上。

```bash
git clone git@server_ip:/path/to/repo.git local-folder
```

2. 就可以在本地与服务器之间进行push/pull。与github等第三方托管服务不同的是，
在自己配置的服务器上查看repo.git目录，不能看到项目中的文件和目录，只有git仓库信息，
因为这里是用`git --bare init`命令在服务器上创建的空仓库，它只负责存储对仓库的修改记录。
如果使用`git init`命令创建仓库，在个人电脑上`push`时会冲突而出现错误。
当然如果使用`git init`创建仓库也有办法解决`push`冲突问题，但不建议。