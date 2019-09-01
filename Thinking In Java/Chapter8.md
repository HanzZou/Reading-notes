# 多态

## 8.1 再论向上转型

只需要一份针对基类类型的代码，就可以解决所有导出类型的问题

## 8.2 转机

将一个方法调用和方法主题联系起来叫做绑定，在程序执行前进行绑定叫做前期绑定，在程序执行期间根据具体类型选择绑定的对象叫做后期绑定（动态绑定或运行时绑定）

Java中除了static和final（private方法属于final）方法外都是后期绑定。虽然可以提高程序效率，但实际上提升并不大，所以应该以设计来决定是否使用final，而不是出于提高性能的角度。

在编译时，编译器不需要获得任何特殊信息就能进行正确的调用，对方法的调用都是通过动态绑定进行的。

缺陷：“覆盖”私有方法，实际上并不是方法的重载
缺陷：域与静态方法，当导出类对象转型为基类引用时，任何域访问操作都将由编译器解析，因此不是多态的。

## 8.3 构造器与多态

一个复杂对象调用构造器的顺序：

1. 调用基类构造器，这个步骤会不断重复递归下去
1. 按声明顺序调用成员的初始化方法
1. 调用导出类构造器的主体

在面对继承的清理问题时，如果为基类和导出类都创建了dispose()方法，在导出类中一定要调用基类的dispose()，不然基类的清理动作就不会发生。

如果对象被多次引用共享，需要计数来决定是否真正对象进行清理

初始化的实际过程：

1. 在其他任何事物发生之前，将分配给对象的存储空间初始化成二进制的零
1. 在前所述那样调用基类构造器。此时，调用的方法是导出类的方法，此时导出类的成员变量还没被初始化
1. 按照声明的顺序调用成员的初始化方法
1. 调用导出类的构造器主体

编写构造器时的准则：尽可能用简单的方式初始化对象，避免调用其他方法
在构造器中可以被安全调用的方法是基类中的final方法

## 8.4 协变返回类型

```Java
class Grain{
    public String toString(){
        return "Grain";
    }
}

class Wheat extends Grain{
    public String toString(){
        return "Wheat";
    }
}

class Mill{
    Grain process() {
        return new Grain();
    }
}

class WheatMill {
    Wheat process() {
        return new Wheat();
    }
}

public class CovariantReturn {
    public static void main(String[] args){
        Mill m = new Mill();
        Grain g = new Grain();
        System.out.println(g);
        m = new WheatMill();
        g = m.process();
        System.out.println(g);
    }
} /* Output:
Grain
Wheat
*///:~
```

## 8.5 用继承进行设计

首先选择“组合”，更加灵活，可以动态选择类型

一条准则：用继承表达行为间的差异，并用字段表达状态上的变化