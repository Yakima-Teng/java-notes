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

