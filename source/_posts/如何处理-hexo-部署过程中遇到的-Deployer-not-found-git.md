---
title: '如何处理 hexo 部署过程中遇到的 Deployer not found: git'
date: 2017-04-23 15:13:46
tags: hexo
categories: 代码如诗
---

对 hexo 进行部署，要进入 hexo 的系统配置`_config.yml`中，找到`deploy`这一项进行修改：

```
deploy:
   type: git
   repo: git@github.com:/xxxxxxxxx/xxxxxxxxxx.github.io.git
   branch: master
```
其中：
- `type`是部署方式
- `repo`是你的仓库地址
- `branch`是你想要施行部署的分支

相信熟悉 git 的朋友对这些都不会陌生，问题就出在`type`上。

#### 遭遇问题和处理过程

- `type`值为`git`，正常步骤下部署，发现`not found: git`
- 改`type`的值为`github`之后，也无法部署，报错变成`not found: github`
```
➜  hexo hexo g -d
INFO  Start processing
ERROR Deployer not found: git
➜  hexo hexo g -d
INFO  Start processing
ERROR Deployer not found: github
```

- 撤掉文件夹重新部署 hexo 的环境
```
➜  hexo npm install     
➜  hexo npm install hexo-deployer-git
hexo-site@0.0.0 /Users/Calvino/development projects/hexo
└── hexo-deployer-git@0.2.0 
```

- 仍然无法部署
```
➜  hexo hexo g -d                    
INFO  Start processing
ERROR Deployer not found: github
➜  hexo hexo g -d
INFO  Start processing
ERROR Deployer not found: git
```

- 确认自己的 hexo 版本
```
➜  hexo hexo -v
hexo: 3.3.1
hexo-cli: 1.0.2
......
```

- 重新用这条命令安装`deployer`，注意和前面命令的区别，加了`--save`
```
➜  hexo npm install hexo-deployer-git --save
hexo-site@0.0.0 /Users/Calvino/development projects/hexo
└── hexo-deployer-git@0.2.0 
```

- 部署成功
```
➜  hexo hexo g -d                           
INFO  Start processing
INFO  Deploy done: git
```