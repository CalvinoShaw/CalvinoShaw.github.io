---
title: 关于 hexo 的主题文件夹因为 modified content 而无法 push 的解决方案
date: 2017-04-23 15:29:30
tags: hexo
---

- 如果主题是经由`clone`安装的，在`push`源文件的时候，会发现即使添加了全部文件，主题文件夹也会提示`modified content`而无法被`staged`
```
➜  hexo git:(file) ✗ git add .
```
```
➜  hexo git:(file) ✗ git status
Changes not staged for commit:
	modified:   themes/next (modified content)
```

- 这种情况下，尝试了几种解决方案

### 尝试一：使用`git rm --cache themes/next`

```
➜  hexo git:(file) ✗ git rm --cache themes/next
rm 'themes/next'
```
```
➜  hexo git:(file) ✗ git status
	deleted:    themes/next
Changes not staged for commit:
	themes/
```
问题仍然没有解决

### 尝试二：删除主题目录下的`.git`文件夹

- 进入主题 next 的文件夹
```
➜  hexo git:(file) ✗ cd /Users/Calvino/development\      projects/hexo/themes/next 
```

- `rm`删除之前`clone`遗留下来的`.git`文件夹
```
➜  next git:(master) ✗ rm -rf .git
```

- 查看远程仓库状态
```
➜  next git:(file) ✗ git remote -v
  origingit@github.com:/CalvinoShaw/CalvinoShaw.github.io.git (fetch)
  origingit@github.com:/CalvinoShaw/CalvinoShaw.github.io.git (push)
```

- 添加未添加成功的 themes 文件夹，但是发现仍然无法添加，甚至无法追踪到主题文件夹（这时候主题文件夹是存在的，但是`git`无法跟踪）
```
➜  hexo git:(file) git add themes/next                          
➜  hexo git:(file) git status
On branch file
Your branch is up-to-date with 'origin/file'.
nothing to commit, working tree clean
```

### 尝试三：手动删除整个 themes 文件夹

- 在尝试二的基础上（删除了主题文件夹下的`.git`文件夹），手动删除 themes 主题文件夹（我这边是把整个文件夹剪切到别的文件夹中），用`git status`查看状态确认删除
```
➜  hexo git:(file) ✗ git status
	deleted:    themes/next
```

- 重新把已删除的文件夹移回原位置，`git status`查看状态，确认移回
```
➜  hexo git:(file) ✗ git status
	deleted:    themes/next
Untracked files:
	themes/
```

- 三步走添加 themes 文件夹
  - 添加
```
➜  hexo git:(file) ✗ git add themes/
➜  hexo git:(file) ✗ git status
	deleted:    themes/next
	new file:   themes/next/.bowerrc
	new file:   themes/next/.editorconfig
......
```
- 提交
```
➜  hexo git:(file) ✗ git commit -m "themes next config and file"
[file d1d8e3e] themes next config and file
 303 files changed, 35068 insertions(+), 1 deletion(-)
 delete mode 160000 themes/next
 create mode 100644 themes/next/.bowerrc
......
```
- 推送到远程仓库
```
➜  hexo git:(file) git push origin file
   a1d0ed7..d1d8e3e  file -> file
```