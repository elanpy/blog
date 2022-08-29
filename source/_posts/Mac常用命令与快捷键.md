---
title: Mac常用命令与快捷键
abbrlink: 845852d9
date: 2022-08-16 16:53:25
tags: 
top_img: http://tva1.sinaimg.cn/large/008lIB40ly1h5cffa4m0oj31kw0w0qv6.jpg
cover: http://tva1.sinaimg.cn/large/008lIB40ly1h5cffa4m0oj31kw0w0qv6.jpg
---

# 常用命令

### 以管理员身份查看占用指定端口进程

```shell
sudo lsof -i:8888|grep LISTEN
```

### 解压压缩包到指定目录

```shell
unzip -d /tmp test.zip
```

### 查找文件

```shell
 find  "要搜索的文件加路径" -name "要查找的文件名(可以使用正则)"
```

### 根据正则表达式删除文件

```shell
ls -a | egrep "frida-gadget-*" | xargs rm -rf
```

-------



# 常用快捷键



| 动作                                     | 快捷键                     |
| :--------------------------------------- | :------------------------- |
| 快速全屏或取消全屏（需要软件支持）       | `control` + `option` + `F` |
| 跳到文本开头/结尾（加 shift 可以选中）   | `command` + `左/右箭头`    |
| 跳到上一次词头/词尾（加 shift 可以选中） | `option` + `左/右箭头`     |
| 反向搜索命令行历史记录                   | `control` + `R`            |
| 终端行清屏                               | `command` + `K`            |
| 终端清除到上一命令                       | `command` + `L`            |
| 左右切换桌面                             | `control` + `左/右箭头`    |
| 新建窗口                                 | `command` + `N`            |
| 新建标签页                               | `command` + `T`            |

