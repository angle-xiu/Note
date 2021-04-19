# note2
## 小程序import 和 include的区别
### import
+ import 有作用域的概念，即只会 import 目标文件中定义的 template，而不会 import 目标文件 import 的 template。

+ 如：C import B，B import A，在C中可以使用B定义的template，在B中可以使用A定义的template，但是C不能使用A定义的template。
``` html
<!-- C.wxml -->
<import src="b.wxml"/>
<template is="A"/>  <!-- Error! Can not use tempalte when not import A. -->
<template is="B"/>
```

### include
+ include 可以将目标文件除了 `<template/> <wxs/>`标签 外的整个代码引入，相当于是拷贝到 include 位置

```
<!-- index.wxml -->
<include src="header.wxml"/>
<view> body </view>
<include src="footer.wxml"/>

<!-- header.wxml -->
<view> header </view>

<!-- footer.wxml -->
<view> footer </view>
```
### import类似于引入一个库，你可以使用里面定义的方法，而include则是将文件里面的代码粘贴到引入的地方，类似于PHP的语法。