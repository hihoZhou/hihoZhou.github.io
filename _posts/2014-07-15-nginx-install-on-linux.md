---
layout: post
title: linux源码编译安装nginx
date: 2014-07-15
categories: blog
tags: [nginx,nginx安装]
description: 今天下午临时定下要出差。已抵浙江，刚刚安顿。明天一早出发，不便多写。但会在工作之余尽量写。写不是义务，写本身就是写的报酬。

---

注：本次编译安装nginx的系统为ubuntu14.04版本,linux系统大同小异,安装目录为/user/local/nginx-1.6.3。





[TOC]

## 1、编译安装PCRE库——为了rewrite

- tar –zxvf pcre-8.32.tar.gz
- cd pcre-8.32
- ./configure --prefix=/user/local/pcre-8.32
- make
- make install




## 2、安装zlib库——为了gzip压缩

- mkdir /user/local/zlib-1.2.8
- tar –zxvf zlib-1.2.8.tar.gz
- cd zlib-1.2.8
- ./configure --prefix=/user/local/zlib-1.2.8
- make
- make install





## 3、安装ssl库——支持ssl加密
- openssl下载地址
- tar -zxvf openssl-1.0.2a.tar.gz
- cd openssl-1.0.2a
- ./config --prefix=/user/local/openssl-1.0.2
- make
- make install

## 4、安装nginx——服务器软件
- nginx下载地址
- tar -zxvf nginx-1.6.3.tar.gz
- cd nginx-1.6.3
- ./configure --prefix=/user/local/nginx-1.6.3 --with-pcre=../pcre-8.32 --with-zlib=../zlib-1.2.8 --with-openssl=/user/local/openssl-1.0.2
- make
- make install



## 5、启动nginx
- sudo /user/local/nginx-1.6.3/sbin/nginx -c /user/local/nginx-1.6.3/conf/nginx.conf

可以使用`ps aux | grep nginx`命令查看nginx是否启动成功
![nginx_start_up_success.jpg](http://7xpyze.com1.z0.glb.clouddn.com/nginx_start_up_success.jpg)

—End—

## 迭代


* 2014年7月15日 19:09:17 初稿



