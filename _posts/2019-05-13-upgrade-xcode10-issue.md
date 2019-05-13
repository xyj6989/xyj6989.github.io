---
layout: post
title:  "更新到xcode10出现的问题解决说明"
date:   2019-05-13 15:41:00 +0800
categories: [iOS, Xcode]
tags: [issue, Xcode, libstdc++.6.0.9]
---

* content
{:toc}

----
## libstdc++.6.0.9
一些老的项目，偶尔会要求更新，结果本地的xcode早就更新到最新版本Xcdoe10了，一打开，全部红艳艳的，惨不忍睹，只能一项一项改。

其中有个比较特殊的，从Xcode10开始，苹果移除了libstdc++.6.0.9，造成一些依赖的SDK无法正常编译。

当然最好的解决办法是及时更新第三方SDK，适配Xcode10，不过确实有些老项目没更新，没办法适配，那只能在Xcode10里重新加入该库了。

点击这里[下载]({{ site.url }}/assets/201905/xcode10issue/libstdc.zip "libstdc文件")

里面有放置说明

enjoy!