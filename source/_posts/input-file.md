---
title: input file兼容问题
date: 2018-01-07 17:25:50
tags:
---

### 一、使用trigger('click')无效

实际应用中，我们往往会通过隐藏input file，而用一个漂亮的按钮来触发input file，实现文件上传，这时就会用到trigger('click'),但是会发现在一些浏览器上不能生效，这是因为input被隐藏的（display:none），解决办法如下：

<!-- more -->

1、给input设置width:0,height:0

2、给input设置opacity:0


### 二、“没有应用可执行操作”问题

h5页在手机上实现上传图片，会用到input file来实现，但在小米、华为手机上触发按钮后，弹出“没有应用可执行操作”，解决办法如下：

将
``` bash
<input  type="file" accept=".jpg,.jpeg,.png,.gif">
```

改成
``` bash
<input  type="file" accept="image/jpg,image/jpeg,image/png,image/gif">
```

如果没有格式限制的话可改成
``` bash
<input  type="file" accept="image/*">
```