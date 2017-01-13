# 封装

面向对象三大特性：封装、继承、多态。

## 1. 概念

将类的某些信息隐藏在类内部，不允许外部程序直接访问，而是通过该类提供的方法来实现对隐藏信息的操作和访问。

## 2. 好处

- 只能通过规定的方法访问数据；
- 隐藏类的实现细节，方便修改和实现；

## 3. 封装的实现步骤

1. 修改属性的可见性（如设为private）;
2. 创建getter/setter方法（用于属性的读写）；
3. 在getter/setter方法中加入属性控制语句（对属性值的合法性进行判断）。

示例：
```
public class Telphone {
    private float screen;

    public float getScreen () {
        return screen;
    }

    public void setScreen (float newScreen) {
        screen = newScreen;
    }
}
```

## Reference

[http://www.imooc.com/video/2360](http://www.imooc.com/video/2360)
