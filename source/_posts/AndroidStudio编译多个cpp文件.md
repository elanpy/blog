---
title: AndroidStudio编译多个cpp文件
abbrlink: 4b46a73e
date: 2022-09-21 11:08:37
tags:
---
先看一下目录结构
![1.png](http://tva1.sinaimg.cn/mw690/008lIB40ly1h6e2f4uzx4j306d075gm3.jpg)

其中cpp的为
```shell
.
|____CMakeLists.txt
|____demo2
| |____CMakeLists.txt
| |____demo2.cpp
|____demo1
| |____CMakeLists.txt
| |____demo1.cpp
```

这里最外层的`CMakeLists.txt`里的内容为
```text
cmake_minimum_required(VERSION 3.18.1)

# 指定编译后so文件存放路径
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/jniLibs/${ANDROID_ABI})

# 指定需要编译的cpp所在的路径
ADD_SUBDIRECTORY(${PROJECT_SOURCE_DIR}/demo1)
ADD_SUBDIRECTORY(${PROJECT_SOURCE_DIR}/demo2)
```

子文件夹内的`CMakeLists.txt`，例如`demo1`下的内容为
```text
# 生成动态库名称、类型、资源文件
add_library(demo1 SHARED demo1.cpp)

# 依赖库
find_library(log-lib log)

# 目标库
target_link_libraries(demo1 ${log-lib})
```

并在文件夹内新建好cpp文件，内部可以便携so层方法


{% note warning no-icon %} 如果发现大量标黄或者提示报错不要慌张，在Build-Refresh Linked C++ Projects刷新一下即可 {% endnote %}

接下来构建并运行项目，看到是正常的，并且也将so文件单独存放到指定文件夹了
![image.png](http://tva1.sinaimg.cn/mw690/008lIB40ly1h6e2oaz6ctj305w06djry.jpg)