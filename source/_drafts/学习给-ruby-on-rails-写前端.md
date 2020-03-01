---
title: 学习给 ruby on rails 写前端
date: 2016-10-31 10:24:51
tags: ruby on rails
categories: 代码如诗
---

## 10.31

### 学习 [Asset Pipeline](http://guides.ruby-china.org/asset_pipeline.html)

- sprockets-rails gem
- MD5 指纹
- “缓存爆裂”（cache busting）
- 生产环境
- 中间件（Sprockets 中间件）
- 脚手架或控制器
- CoffeeScript
- ExecJS 的运行时
- Turbolinks
- Capistrano
- Expires 报头
- GZip 压缩
- Apache
- Nginx
- YUI CSS compressor
- closure-compiler
- uglifier
- yui-compressor

### 用到的库

- #### [tinymce]()

  TinyMCE 是一个轻量级的基于浏览器的所见即所得编辑器，支持目前流行的各种浏览器，由 JavaScript 写成。功能配置灵活简单（两行代码就可以将编辑器嵌入网页中），支持 AJAX。另一特点是加载速度非常快，如果你的服务器采用的脚本语言是 PHP，那还可以进一步优化。最重要的是，TinyMCE是一个根据 LGPL license 发布的自由软件，你可以把它用于商业应用。
  [中文使用教程](http://www.jb51.net/web/78618.html)

- #### [Jcrop](https://github.com/tapmodo/Jcrop)
  Jcrop 是一个功能强大的 jQuery 图像裁剪插件，结合后端程序（例如：PHP）可以快速的实现图片裁剪的功能。
  [中文API](http://code.ciaoca.com/jquery/jcrop/)

- #### [ZeroClipboard](https://github.com/zeroclipboard/zeroclipboard)
  使用 ZeroClipboard 可以简单的将内容复制到剪贴板，通过 Adobe Flash 和 JavaScript 来实现。“Zero” 意义为这个类库没有界面，界面需要由你来建立。
  [中文API](http://code.ciaoca.com/javascript/zeroclipboard/)
  [使用教程](http://www.365mini.com/page/zeroclipboard-2_x-quick-start.htm)

- #### [qrcode](https://github.com/jeromeetienne/jquery-qrcode)
  qrcode 其实是通过使用 jQuery 实现图形渲染，画图，生成二维码，支持`canvas`（HTML5）和 `table` 两种方式
  [使用](http://www.helloweba.com/view-blog-226.html)

- #### [jquery_ujs](https://github.com/rails/jquery-ujs)
  UJS 是为 Ruby on Rail 框架开发的一个不起眼的脚本支持文件，但是它不会严格地绑定到任何特定的后端。你可以把它拖放到任何应用程序中，从而完成以下这些事情：
  1. 确认对话框的各种操作
  2. 从超链接获得 non-GET 请求
  3. 使表格和超链接呈递的数据与 Ajax 的同步
  4. 表单提交成功后，按钮自动关闭，以防止双击

- #### [jquery.pep.js](http://pep.briangonzalez.org/)
  JQUERY.PEP.JS 是一个轻量级的 jQuery 插件，结合了 jQuery 动画和 CSS3 动画，在移动和桌面设备上实现 Kinetic Drag。JQUERY.PEP.JS支持自定义启动、停止、休眠及拖拽事件、约束父体或视窗对象。
  [中文使用说明](http://www.uedsc.com/jquery-pep-js.html)

- #### [sui](http://sui.taobao.org/sui/docs/)
  SUI 是一套基于 bootstrap 开发的前端组件库，同时她也是一套设计规范。通过 SUI，可以非常方便的设计和实现精美的页面。

- #### [swiper](https://github.com/nolimits4web/swiper/)
  Swiper 是纯 javascript 打造的滑动特效插件，面向手机、平板电脑等移动终端。Swiper 能实现触屏焦点图、触屏Tab切换、触屏多图切换等常用效果。
  [swiper 2中文网](http://2.swiper.com.cn/)
  [swiper 3中文网](http://www.swiper.com.cn/)

### 疑问
- 有一点要注意，如果静态资源不会在清单文件中引入，就要添加到预编译的文件列表中，否则在生产环境中就无法访问文件。
- 如果程序启用了 `Asset Pipeline`，且在当前环境中没有禁用，那么这个文件会经由 `Sprockets` 伺服。如果文件的存放位置是 `public/assets/rails.png`，则直接由网页服务器伺服。
- 如果想使用多个 `Sass` 文件，应该使用 Sass 中的 `@import` 规则，不要使用 `Sprockets` 指令。如果使用 `Sprockets` 指令，`Sass` 文件只出现在各自的作用域中，`Sass` 变量和混入只在定义所在文件中有效。为了达到 require_tree 指令的效果，可以使用通配符，例如 `@import "*"` 和 `@import "**/*"`。详情参见 `sass-rails` 的文档。
- 前文举过例子，生成 `projects` 控制器时会创建 `app/assets/javascripts/projects.js.coffee` 和 `app/assets/stylesheets/projects.css.scss` 两个文件。
- 关闭调试功能后，`Sprockets` 会预处理所有文件，然后合并。关闭调试功能后，前文的清单文件生成的 HTML 如下：`<script src="/assets/application.js"></script>`
- 在开发环境中也可启用压缩功能，检查是否能正常运行。需要调试时再禁用压缩即可。（如何启用？？？？）
- Rails 提供了一个 `rake` 任务用来编译清单文件中的静态资源和其他相关文件。编译后的静态资源保存在 `config.assets.prefix` 选项指定的位置。默认是 `/assets` 文件夹。部署时可以在服务器上执行这个任务，直接在服务器上编译静态资源。