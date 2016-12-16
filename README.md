#内容介绍

该笔记本为学习Web过程中的做的一些记录。
Gitbook地址：[https://yakima-teng.gitbooks.io/java-notes/content/](https://yakima-teng.gitbooks.io/java-notes/content/)

#关于Gitbook的使用

1、npm install -g gitbook-cli，装完后gitbook -V查看版本号以确认是否安装成功。这一句我的cmd里显示installing gitbook然后需要等很久。我是翻墙后装起来的，翻墙之前等了很久也不知道能不能装起来就没继续等了。

2、在项目根目录下撰写README.md和SUMMARY.md。后者示例如下：

```
# Summary

* [简介](README.md)
* [第一章](chapter1/README.md)
    * [第一节](chapter1/section1.md)
    * [第二节](chapter1/section2.md)
* [第二章](chapter2/README.md)
    * [第一节](chapter2/section1.md)
    * [第二节](chapter2/section2.md)
* [结束](end/README.md)
```

3、在项目根目录运行gitbook init，生成图书目录结构。

4、运行gitbook serve可以在本地进行预览。

5、在gitbook书本的设置里找到GitHub=>Webhook，根据该页提示在github上添加webhook，这样github仓库上push新变化时，会通知gitbook以便后者进行更新。
