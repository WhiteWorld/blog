---
layout: post
title: "Ubuntu 12.04上部署Rails应用"
description: ""
category: rails
tags: [deploy, ubuntu, vps]
---
{% include JB/setup %}


1.  使用Nginx + Passenger方式

  - 步骤

    基本步骤参考: [Ubuntu 12.04 上使用 Nginx Passenger 部署 Ruby on Rails ](https://github.com/ruby-china/ruby-china/wiki/Ubuntu-12.04-%E4%B8%8A%E4%BD%BF%E7%94%A8-Nginx-Passenger-%E9%83%A8%E7%BD%B2-Ruby-on-Rails )

  - 注意
    - 如果提示没有安装JS运行环境，则可安装nodejs解决 `sudo apt-get install nodejs`
    - 默认Passenger以Production方式运行Rails程序，如果要以Development方式运行，在nginx的配置文件example.com.conf中加入一行，` rails_env development;`
    - 如果使用VPS，h如[][阿里云](http://www.aliyun.com/)


