---
title: frida使用中可能遇到的问题
abbrlink: ee81aec9
date: 2022-09-28 17:10:50
tags:
top_img: 'http://tva1.sinaimg.cn/mw690/008lIB40ly1h6zz8xi4txj335s23y7wk.jpg'
cover: 'http://tva1.sinaimg.cn/mw690/008lIB40ly1h6zz8xi4txj335s23y7wk.jpg'

---
# unable to find export
这个错误是由于没有找到so文件或者native方法导致的
解决方法：
1. 检查frida-server是否成功开启，包括版本是否对应
2. 通过下面js代码查看当前已加载的模块，并且是否so文件对应（曾被坑过：demo3.so与libdemo3.so）
```javascript
Java.perform(function(){
//枚举当前加载的模块
var process_Obj_Module_Arr = Process.enumerateModules();
for(var i = 0; i < process_Obj_Module_Arr.length; i++) {
   //包含"lib"字符串的
   if(process_Obj_Module_Arr[i].path.indexOf("lib")!=-1)
   {
       console.log("模块名称:",process_Obj_Module_Arr[i].name);
       console.log("模块地址:",process_Obj_Module_Arr[i].base);
       console.log("大小:",process_Obj_Module_Arr[i].size);
       console.log("文件系统路径",process_Obj_Module_Arr[i].path);
   }
}
});
```