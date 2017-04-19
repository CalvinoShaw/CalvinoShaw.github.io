---
title: 命令行常见操作
date: 2016-10-29 09:43:03
tags: 命令行
---

## **命令行常见操作**

`cd`

`ls` 查看文件

`ls -ah` 查看隐藏文件

`mkdir learngit` 创建文件夹 learngit

`pwd` 显示当前目录

## **安装git**

`$ git config --global user.name "Calvino"`

`$ git config --global user.email "xiaobingyang_007@126.com"`

注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

## **Git常用**

`git add`

`git commit -m "eeeeee"`

`git status`

`git rm test.txt`

`git diff`

`git checkout --readme.txt` 丢弃工作区的修改

`git reset HEAD readme.txt`

`git diff HEAD -- readme.txt` 查看工作区和版本库里面最新版本的区别

`cat one.txt` 查看 one.txt 文件的详细内容

`git log`

<u>**`git log --pretty=oneline`**</u>

`git reset --hard HEAD^`

`git reflog`

`rm test.txt`

``

## **分支管理**

`git checkout -b dev` 创建分支 dev 并切换，相当于以下两条：

- `git branch dev`
- `git checkout dev`

`git branch` 查看当前分支

`git merge dev` 位于 master 分支上的时候合并 dev分支

`git branch -d dev` 删除 dev 分支

`git log --graph --pretty=oneline --abbrev-commit` 查看分支合并情况

`git log --graph` 查看分支合并图

## **远程仓库**

`git remote add origin git@github.com:CalvinoShaw/learngit.git`

`git push -u origin master`

`git push origin master`

`git clone git@github.com:michaelliao/gitskills.git`