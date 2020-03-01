---
title: BEM
date: 2016-10-28 15:31:45
tags: CSS
categories: 代码如诗
---

## 相关定义：

BEM代表块（Block），元素（Element），修饰符（Modifier）。

命名模式：

`.block{}`
`.block__element{}`
`.block--modifier{}`

---

## 相关博文 & 资源：

BEM的定义：http://www.w3cplus.com/css/bem-definitions.html

BEM的50道阴影：http://www.w3cplus.com/css/fifty-shades-of-bem.html

BEM思想之彻底弄清BEM语法：http://www.w3cplus.com/css/mindbemding-getting-your-head-round-bem-syntax.html

XJST仓库：https://github.com/veged/xjst

---

## 重要文摘：

复用一个块也意味着复用它的行为，也就是它所绑定的JavaScript。

所以一个块必须“知道”关于它自己的一切。为了实现一个块，要用我们所用到的所有技术来描述清楚它的外观和行为，我们把这叫多语言机制。

多语言描述一个块的时候涉及实现这个块的外观和功能的所有编程语言（技术）。

想让一个块像一个UI元素一样展现在页面上，我们需要用下面这些技术来实现它：

-  模板（XSL，TT2，JavaScript等等），把块的声明转换成HTML代码
-  CSS，描述块的外观
-  JavaScript，如果块有动态行为的话
-  图片
-  文档

构成一个块的每样东西都可以作为一种块技术。