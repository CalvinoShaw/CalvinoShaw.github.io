---
title: grunt自动化初探
date: 2016-11-02 16:23:29
tags: grunt
categories: 代码如诗
---

# 初步学习使用grunt

---

## 所用插件
- uglify
- jshint
- csshint
- watch

---

## jshint

### jshint 常见错误
- [Missing "use strict" statement.](http://stackoverflow.com/questions/1335851/what-does-use-strict-do-in-javascript-and-what-is-the-reasoning-behind-it)
- `Missing semicolon.`
- `'c' is not defined.`
- `Bad option: '鎻掍欢鐨勯厤缃俊鎭▒'.`（这里出现了乱码，但应该不是乱码的原因导致报错，TODO...）

---

## csshint

### 关于 csshint

[csslint](http://csslint.net/)
[github repo](https://github.com/gruntjs/grunt-contrib-csslint)
[css lint是有害的](http://caibaojian.com/csslint-is-harmful.html)
[CSS LINT,优化你的CSS样式表](http://caibaojian.com/csslint.html)

#### csshint 常见错误
```
Linting src/test-csslint.css...ERROR
[L59:C1]
WARNING: Rule doesn't have all its properties in alphabetical order. Assure properties are in alphabetical order (order-alphabetical) Browsers: All```
```