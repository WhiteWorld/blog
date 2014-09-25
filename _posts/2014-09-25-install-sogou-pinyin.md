---
layout: post
title: "Ubuntu 14.04 LTS 安装 sogou 拼音输入法"
description: ""
category: "记录"
tags: [array, problem, LeetCode]
---
{% include JB/setup %}

1. 不要删除iBus, 删除后会导致系统设置出现缺失，[参见](http://jingyan.baidu.com/article/375c8e19985a2125f2a229cb.html).
2. 按照[官方安装指南](http://pinyin.sogou.com/linux/help.php)操作。如果是Kylin版本，直接下载deb包双击安装，普通的12.04 LTS要像12.04一样添加源，安装fcitx先。
3. 修改系统输入法，系统设置-语言支持-键盘输入方式 选择fcitx，应用到整个系统/
4. 重启电脑。
