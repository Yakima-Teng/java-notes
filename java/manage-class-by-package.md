# 使用包管理Java中的类

## 1、包的作用

- 管理Java文件；
- 解决同名文件冲突。

## 2、定义包：package 包名

注：必须放在Java源程序的第一行，包名间可以使用“.”号隔开，如：com.imooc.MyClass

## 3、系统中的包

java.(功能).(类)
java.lang.(类)包含java语言基础的类
java.util.(类)包含java语言中各种工具类
java.io.(类)包含输入、输出相关功能的类

## 4、包的使用

可以通过import关键字，在某个文件中使用其他文件中的类。如：import com.imooc.music.MyClass。

Java中，包的命名规范是全小写字母拼写，虽然用大写字母时编译器不会报错，但此举不规范。

使用的时候可以通过星号加载某个包下的所有文件：
```
com.imooc.*
```
也可以加载某个具体子包下的所有文件：
```
com.imooc.music.*
```

## Reference

[http://www.imooc.com/video/2371](http://www.imooc.com/video/2371)
