---
title: 关于 hexo 文件夹内容无法 push 到 github 上的解决方案
date: 2017-04-23 14:00:11
tags: hexo
categories: 代码如诗
---

- 进入 hexo 的文件目录
```
➜  hexo git:(file) ✗ cd /Users/Calvino/development\ projects/hexo/themes/next 
```

- 删掉 clone 主题 next 的时候留下来的 `git`文件夹
```
➜  next git:(master) ✗ rm -rf .git
```

- 查看这时候的远程仓库详情，确认已经是自己的部署仓库
```
➜  next git:(file) ✗ git remote -v
  origingit@github.com:/CalvinoShaw/CalvinoShaw.github.io.git (fetch)
  origingit@github.com:/CalvinoShaw/CalvinoShaw.github.io.git (push)
```

- 查看状态，三步走添加提交推送，成功
```
➜  hexo git:(file) ✗ git status
  modified:   _config.yml
  new file:   source/_posts/BEM.md
➜  hexo git:(file) ✗ git add .
➜  hexo git:(file) ✗ git commit -m "basic version of hexo in nexT"
➜  hexo git:(file) git push origin file
To github.com:/CalvinoShaw/CalvinoShaw.github.io.git
   bcc0bcd..a1d0ed7  file -> file
```