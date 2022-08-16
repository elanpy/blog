---
title: Mac查看端口占用
abbrlink: 845852d9
date: 2022-08-16 16:53:25
tags:
---

# Mac查看端口占用

```shell
sudo lsof -i:80|grep LISTEN
```