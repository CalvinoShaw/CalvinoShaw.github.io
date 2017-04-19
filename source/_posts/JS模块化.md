---
title: JS模块化
date: 2016-10-30 23:01:02
tags: js
---

无封装
简单封装：Namespace 模式
匿名闭包 ：IIFE 模式
模块模式：开始引入依赖

只有“封装”是不够的，我们还需要考虑“加载”

### 2009 - [LABjs](http://www.oschina.net/p/labjs)
LABjs 是一个很小的 JavaScript 工具，用来根据需要加载 JavaScript 文件，通过使用该工具可以提升页面的性能，避免加载不需用到的 JavaScript 文件

### 2009 - [YUI3](http://yuilibrary.com/)
YUI 是Yahoo!的一个开源项目，包含了前端开发中的CSS、测试、文档、压缩等一系列工具和文档，其中YUI 的JavaScript 库是一个优秀的JavaScript 框架。从YUI 2 到YUI 3，YUI 一直在不断地迭代，一直走在前端开发的最前列，就像它宣称的那样："YUI 是一个构建富交互Web 应用的免费开源JavaScript 和CSS 库。
[YUI3 repo](https://github.com/yui/yui3)
[YUI Loader(Combo)](http://yuilibrary.com/yui/docs/yui/loader.html)
[YUI 3 Cookbook 中文版](http://book.51cto.com/art/201304/387814.htm)
2014年雅虎宣布[停止开发](http://www.infoq.com/cn/news/2014/09/yahoo-drop-axe-YUI)


合并 Concat
压缩 Minify
混淆 Uglify

### 2009.8 - [CommonJS](http://www.commonjs.org/)
[CommonJS 规范](http://zhaoda.net/webpack-handbook/commonjs.html)
[CommonJS 规范](http://javascript.ruanyifeng.com/nodejs/module.html)

### 2011 - [RequireJS](http://requirejs.org/)
首先，加载的时候，浏览器会停止网页渲染，加载文件越多，网页失去响应的时间就会越长；其次，由于js文件之间存在依赖关系，因此必须严格保证加载顺序，依赖性最大的模块一定要放到最后加载，当依赖关系很复杂的时候，代码的编写和维护都会变得困难。
RequireJS的诞生，就是为了解决这两个问题。RequireJS的目标是鼓励代码的模块化，它使用了不同于传统`<script>`标签的脚本加载步骤。可以用它来加速、优化代码，但其主要目的还是为了代码的模块化。
[中文API](http://www.requirejs.cn/)

### [2011 - SeaJS](http://seajs.org/docs/#intro)

### [AMD](https://github.com/amdjs/amdjs-api/wiki/AMD)
AMD是"Asynchronous Module Definition"的缩写，意思就是"异步模块定义"。它采用异步方式加载模块，模块的加载不影响它后面语句的运行。所有依赖这个模块的语句，都定义在一个回调函数中，等到加载完成之后，这个回调函数才会运行。

### NPM包管理工具
#### [2011 / 2014 stable - browserify](http://browserify.org/)
[Watchify](https://www.npmjs.com/package/watchify)browserify 的实时编译
express
pm2
grunt
npm
karma
bower

### [2014 - webpack](https://webpack.github.io/)
Webpack 是当下最热门的前端资源模块化管理和打包工具。它可以将许多松散的模块按照依赖和规则打包成符合生产环境部署的前端资源。还可以将按需加载的模块进行代码分隔，等到实际需要的时候再异步加载。通过 loader 的转换，任何形式的资源都可以视作模块，比如 CommonJs 模块、 AMD 模块、 ES6 模块、CSS、图片、 JSON、Coffeescript、 LESS 等。
[GitBook - Webpack 中文指南](http://zhaoda.net/webpack-handbook/)
应用：NodeJS

### [2015 - Babel](https://babeljs.io/)

### [babel-loader](https://github.com/babel/babel-loader)

Babel is a compiler for writing next generation JavaScript.