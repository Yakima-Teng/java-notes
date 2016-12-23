# 第二节: Maven的使用

## 编写POM

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.juvenxu.mvnbook</groupId>
  <artifactId>hello-world</artifactId>
  <version>1.0-SNAPSHOT</version>
  <name>Maven Hello World Project</name>
</project>
```

代码的第一行是XML头，指定了该xml文档的版本和编码方式。紧接着是project元素，project是所有pom.xml的根元素，它还声明了一些POM相关的命名空间及xsd元素，虽然这些属性不是必须的，但使用这些属性能够让第三方工具（如IDE中的XML编辑器）帮助我们快速编辑POM。
根元素下的第一个子元素modelVersion指定了当前POM模型的版本，对于Maven2及Maven 3来说，它只能是4.0.0。
这段代码中最重要的是groupId，artifactId和version三行。这三个元素定义了一个项目基本的坐标，在Maven的世界，任何的jar、pom或者war都是以基于这些基本的坐标进行区分的。
groupId定义了项目属于哪个组，这个组往往和项目所在的组织或公司存在关联，譬如你在googlecode上建立了一个名为myapp的项目，那么groupId就应该是com.googlecode.myapp，如果你的公司是mycom，有一个项目为myapp，那么groupId就应该是com.mycom.myapp。本书中所有的代码都基于groupId com.juvenxu.mvnbook。
artifactId定义了当前Maven项目在组中唯一的ID，我们为这个Hello World项目定义artifactId为hello-world，本书其他章节代码会被分配其他的artifactId。而在前面的groupId为com.googlecode.myapp的例子中，你可能会为不同的子项目（模块）分配artifactId，如：myapp-util、myapp-domain、myapp-web等等。
顾名思义，version指定了Hello World项目当前的版本——1.0-SNAPSHOT。SNAPSHOT意为快照，说明该项目还处于开发中，是不稳定的版本。随着项目的发展，version会不断更新，如升级为1.0、1.1-SNAPSHOT、1.1、2.0等等。本书的6.5小节会详细介绍SNAPSHOT，第13章介绍如何使用Maven管理项目版本的升级发布。
最后一个name元素声明了一个对于用户更为友好的项目名称，虽然这不是必须的，但我还是推荐为每个POM声明name，以方便信息交流。
没有任何实际的Java代码，我们就能够定义一个Maven项目的POM，这体现了Maven的一大优点，它能让项目对象模型最大程度地与实际代码相独立，我们可以称之为解耦，或者正交性，这在很大程度上避免了Java代码和POM代码的相互影响。比如当项目需要升级版本时，只需要修改POM，而不需要更改Java代码；而在POM稳定之后，日常的Java代码开发工作基本不涉及POM的修改。

## Reference
- [《Maven实战》（国内首本Maven著作）（Maven的安装、配置及使用入门） - 华章图书 - ITeye知识库频道](http://hzbook.group.iteye.com/group/wiki/2872-Maven-in-action#3347)
