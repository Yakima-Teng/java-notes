# 注解Annotation

从JDK5开始，Java增加了Annotation(注解)，Annotation是代码里的特殊标记，这些标记可以在编译、类加载、运行时被读取，并执行相应的处理。通过使用Annotation，开发人员可以在不改变原有逻辑的情况下，在源文件中嵌入一些补充的信息。代码分析工具、开发工具和部署工具可以通过这些补充信息进行验证、处理或者进行部署。

Annotation提供了一种为程序元素（包、类、构造器、方法、成员变量、参数、局域变量）设置元数据的方法。Annotation不能运行，它只有成员变量，没有方法。Annotation跟public、final等修饰符的地位一样，都是程序元素的一部分，Annotation不能作为一个程序元素使用。

## 1 定义Annotation

定义新的Annotation类型使用@interface关键字（在原有interface关键字前增加@符号）。定义一个新的Annotation类型与定义一个接口很像，例如：

```
public @interface Test{
    ....
}
```

定义完该Annotation后，就可以在程序中使用该Annotation。使用Annotation，非常类似于public、final这样的修饰符，通常，会把Annotation另放一行，并且放在所有修饰符之前。例如：

```
@Test
public class MyClass{
    ....
}
```

### 1.1 成员变量

Annotation只有成员变量，没有方法。Annotation的成员变量在Annotation定义中以“无形参的方法”形式来声明，其方法名定义了该成员变量的名字，其返回值定义了该成员变量的类型。例如：

```
public @interface MyTag{
    string name();
    int age();
}
```

示例中定义了2个成员变量，这2个成员变量以方法的形式来定义。

一旦在Annotation里定义了成员变量后，使用该Annotation时就应该为该Annotation的成员变量指定值。例如：

```
public class Test{
    @MyTag(name="红薯"，age=30)
    public void info(){
    ......
    }
}
```

也可以在定义Annotation的成员变量时，为其指定默认值，指定成员变量默认值使用default关键字。示例：

```
public @interface MyTag{
    string name() default "我兰";
    int age() default 18;
}
```

如果Annotation的成员变量已经指定了默认值，使用该Annotation时可以不为这些成员变量指定值，而是直接使用默认值。例如：

```
public class Test{
    @MyTag
    public void info(){
    ......
    }
}
```

根据Annotation是否包含成员变量，可以把Annotation分为如下两类：

- 标记Annotation：没有成员变量的Annotation被称为标记。这种Annotation仅用自身的存在与否来为我们提供信息，例如@override等。

- 元数据Annotation：包含成员变量的Annotation。因为它们可以接受更多的元数据，因此被称为元数据Annotation。

### 1.2 元注解

在定义Annotation时，也可以使用JDK提供的元注解来修饰Annotation定义。JDK提供了如下4个元注解（注解的注解，不是上述的“元数据Annotation”）：

- @Retention
- @Target
- @Documented
- @Inherited

#### 1.2.1 @Retention

@Retention用于指定Annotation可以保留多长时间。

@Retention包含一个名为“value”的成员变量，该value成员变量是RetentionPolicy枚举类型。使用@Retention时，必须为其value指定值。value成员变量的值只能是如下3个：

- RetentionPolicy.SOURCE：Annotation只保留在源代码中，编译器编译时，直接丢弃这种Annotation。
- RetentionPolicy.CLASS：编译器把Annotation记录在class文件中。当运行Java程序时，JVM中不再保留该Annotation。
- RetentionPolicy.RUNTIME：编译器把Annotation记录在class文件中。当运行Java程序时，JVM会保留该Annotation，程序可以通过反射获取该Annotation的信息。

示例：

```
package com.demo1;

import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;

//name=value形式
//@Retention(value=RetentionPolicy.RUNTIME)

//直接指定
@Retention(RetentionPolicy.RUNTIME)
public @interface MyTag{
    String name() default "我兰";
}
```

如果Annotation里只有一个名为“value“的成员变量，使用该Annotation时，可以直接使用XXX(val)形式为value成员变量赋值，无须使用name=val形式。


## Reference
- [Java注解Annotation基础](http://www.open-open.com/lib/view/open1423558996951.html)
