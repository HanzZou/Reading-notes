# 类型信息

运行时类型信息使得你可以在程序运行时发现和使用类型信息

## 14.1 为什么需要RTTI

在Java中，所有的类型转换都是在运行时进行正确性检查的，在运行时识别一个对象的类型

## 14.2 Class对象

类型信息在运行时的表示是由Class对象完成的，它包含与类有关的信息，由“类加载器”子系统生成Class对象

类加载器子系统包含一条类加载器链，只有一个原生类加载器，是JVM实现的一部分，加载可信类(包括Java API类)，通常从本地盘加载。

当程序创建第一个对类的静态成员的引用时，就会加载这个类。构造器是类的静态方法，使用new操作符创建类的新对象会被当做对类的静态成员的引用。

Class.forName(CLASSNAME)可以获得这个类的对象的引用