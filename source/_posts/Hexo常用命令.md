---
title: Hexo常用命令
top_img: http://tva1.sinaimg.cn/large/008lIB40ly1h3zth54jhuj32yo1o0nph.jpg
cover: http://tva1.sinaimg.cn/large/008lIB40ly1h3zth54jhuj32yo1o0nph.jpg
tags: [blog, hexo]
categories: [python]
abbrlink: 24caea6b
date: 2022-07-08 16:13:28
---

# Hexo常用命令

### hexo init

`hexo init` 用于初始化hexo， 新建文件夹做为网站的根目录

```shell
hexo init [folder]
```

- `floder` 为可选参数，用于指定初始化目录的路径，若无指定则默认为当前目录

### hexo new

`hexo new` 用于新建文章，同时也可以简写为 `hexo n`

```shell
hexo new [layout] <title>
```

- `alyout`  **可选参数**， 用于指定文章类型，若无指定则默认由配置文件中的default_layout选择决定（默认为post）
- `title` **必填参数**，用于指定文章标题，如果参数值中含有空格，则需要使用双引号包围

### hexo generate

`hexo generate` 用于生成静态文件，一般可以简写为 `hexo g`

```shell
hexo generate
```

### hexo server

`hexo server` 用于启动本地服务器，一般可以简写为 `hexo s`

```shell
hexo server
```

- `-port` 选填，指定服务器端口，默认为 4000，可简写为 `-p`
- `-ip` 选填， 指定服务器IP地址，默认为 0.0.0.0， 可简写为`-i`
- `-static`  选填，静态模式，仅提供public文件夹中的文件并禁用文件监视

{% note warning no-icon %} 运行hexo依赖hexo-server插件 {% endnote %}

```shell
npm install hexo-server --save
```

### hexo deploy

`hexo deploy` 命令用于部署网站，一般可以简写为`hexo d`

```shell
hexo deploy
```

{% note warning no-icon %} 部署前需要填写_config.yml配置文件中的deploy {% endnote %}

### hexo clean

`hexo clean`用于清理缓存文件

```shell
hexo clean
```

# 总结

命令之间可以使用`&&`链接，进行连续执行

#### 例：

1. 清理缓存 -> 2. 生成静态文件 -> 3. 开启本地服务

```shell
hexo clean && hexo g && hexo s
```

2. 清理缓存 -> 2. 生成静态文件 -> 3. 文件部署

```shell
hexo clean && hexo g && hexo d
```

