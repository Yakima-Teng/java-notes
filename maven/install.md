# Installation of Maven

## Installation in Windows System

First of all, make sure that JAVA is correctly installed in your computer and command "java -version" is available in cmd tool.

Download .zip file from official Maven website, unzip it in your computer.

Then add path (e.g. D:\bin\apache-maven-3.0\bin) of the bin folder in your unziped folder to the environment variable Path.

Open you cmd tool, type
```
mvn -v
```
and see if this command works. If it works, then you have already installed maven in your computer.


## Structure of Maven Folder

/bin: scripts run by type mvn in cmd tool;

/boot: for most people, there is no need to care about this folder;

/conf: 该目录包含了一个非常重要的文件settings.xml。直接修改该文件，就能在机器上全局地定制Maven的行为。一般情况下，我们更偏向于复制该文件至~/.m2/目录下（这里~表示用户目录），然后修改该文件，在用户范围定制Maven的行为。本书的后面将会多次提到该settings.xml，并逐步分析其中的各个元素。

/lib: 该目录包含了所有Maven运行时需要的Java类库，Maven本身是分模块开发的，因此用户能看到诸如mavn-core-3.0.jar、maven-model-3.0.jar之类的文件，此外这里还包含一些Maven用到的第三方依赖如common-cli-1.2.jar、google-collection-1.0.jar等等。（对于Maven 2来说，该目录只包含一个如maven-2.2.1-uber.jar的文件原本各为独立JAR文件的Maven模块和第三方类库都被拆解后重新合并到了这个JAR文件中）。可以说，这个lib目录就是真正的Maven。关于该文件，还有一点值得一提的是，用户可以在这个目录中找到Maven内置的超级POM。

其他: LICENSE.txt记录了Maven使用的软件许可证Apache License Version 2.0； NOTICE.txt记录了Maven包含的第三方软件；而README.txt则包含了Maven的简要介绍，包括安装需求及如何安装的简要指令等等。

## 关于~/.m2

在讲述该小节之前，我们先运行一条简单的命令：mvn help:system。该命令会打印出所有的Java系统属性和环境变量，这些信息对我们日常的编程工作很有帮助。这里暂不解释help:system涉及的语法，运行这条命令的目的是为了让Maven执行一个真正的任务。我们可以从命令行输出看到Maven会下载maven-help-plugin，包括pom文件和jar文件。这些文件都被下载到了Maven本地仓库中。
现在打开用户目录，比如当前的用户目录是C:\Users\Juven Xu\，你可以在Vista和Windows7中找到类似的用户目录。如果是更早版本的Windows，该目录应该类似于C:\Document and Settings\Juven Xu\。在基于Unix的系统上，直接输入cd 回车，就可以转到用户目录。为了方便，本书统一使用符号 ~ 指代用户目录。
在用户目录下，我们可以发现.m2文件夹。默认情况下，该文件夹下放置了Maven本地仓库.m2/repository。所有的Maven构件（artifact）都被存储到该仓库中，以方便重用。我们可以到~/.m2/repository/org/apache/maven/plugins/maven-help-plugins/目录下找到刚才下载的maven-help-plugin的pom文件和jar文件。Maven根据一套规则来确定任何一个构件在仓库中的位置，这一点本书第6章将会详细阐述。由于Maven仓库是通过简单文件系统透明地展示给Maven用户的，有些时候可以绕过Maven直接查看或修改仓库文件，在遇到疑难问题时，这往往十分有用。
默认情况下，~/.m2目录下除了repository仓库之外就没有其他目录和文件了，不过大多数Maven用户需要复制M2_HOME/conf/settings.xml文件到~/.m2/settings.xml。这是一条最佳实践。

## Reference
- [《Maven实战》（国内首本Maven著作）（Maven的安装、配置及使用入门） - 华章图书 - ITeye知识库频道](http://hzbook.group.iteye.com/group/wiki/2872-Maven-in-action#3347)
