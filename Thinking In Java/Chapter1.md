# 对象导论

## 1.1 抽象过程

Java所基于语言smalltalk的五个基本特性：

- 万物皆为对象
- 程序是对象的集合，它们通过发送消息来告知彼此所要做的
- 每个对象都有自己的由其他对象所构成的存储
- 每个对象都拥有类型
- 某一特定类型的所有对象都可以接受同样的消息

***对象具有状态、行为和标识***

## 1.2 每个对象都有一个接口

面向对象程序设计的挑战之一，就是在问题空间的元素和解空间的对象之间创建一对一的映射。

## 1.3 每个对象都提供服务

将对象看作是服务提供者有助于提高对象的内聚性

## 1.4 被隐藏的具体实现

访问控制的存在原因：

- 让客户端程序员无法触及她们不应该触及的部分（对客户端程序员来说是一种服务）
- 允许库设计者可以改变类内部的工作方式而不用担心会影响到客户端程序员

## 1.5 复用具体实现

代码复用是面向对象程序设计语言所提供的最了不起的优点之一

最简单的复用某个类的方式就是直接使用该类的一个对象（实例化），或者将那个类的一个对象置于某个新类中（组合）

对于继承优先考虑组合

## 1.6 继承

通过发送给类的消息的类型可知类的类型，所以也就意味着导出类与基类具有相同的类型

## 1.7 伴随多态的可互换方法

调用泛化类型对象的方法时，如何确定调用哪个子类的代码？答案也是面向对象程序设计最重要的：编译器不可能产生传统意义上的函数调用。直到程序运行时，才能确定代码的地址（后期绑定）。Java使用一段特殊的代码来替代绝对地址调用，它使用在对象中存储的信息来计算方法体的地址。


```
doSomething(Shape shape){
	shape.erase();
	//...
	shape.draw();
}

doSomething(circle);//Shape的子类型Circle对象
doSomething(line);//Shape的子类型Line对象
```
将导出类看作是它的基类的过程称为向上转型(upcasting)

## 1.8 单根继承结构

使用C++来进行完全的面向对象程序设计时，需要构建自己的集成体系，来提供其他OOP语言内置的便利。单根继承极大简化了参数传递，是垃圾回收器的实现变得容易很多。

## 1.9 容器

对于未知的空间需求，创建“容器”（也叫集合）这种对象类型来解决这类问题。可以自由扩充自己以容纳置于其中的东西。

容器的选择要着眼于具体问题的需求，每种容器都有灵活解决某一类问题的接口。

参数化类型机制：限定容器可以保存对象的类型。参数化类型，也就是范型。

## 1.10 对象的创建和生命期

在堆中动态创建对象

Java提供“垃圾回收器”的机制，自动发现对象何时不再被使用，并自动释放对象占用的内存。

## 1.11 异常处理

## 1.12 并发编程

Java程序员不需要关心机器有多个处理器还是一个处理器

Java并发的隐患：共享资源

Java的并发内置于语言中，有大量的库进行支持

## 1.13 Java与Internet

一种常见的web标准是构建在CGI之上，最常见的动作是运行“cgi-bin”这个程序。

客户端编程的解决方案：插件、脚本语言、Java Applet、.NET和C#、Internet和Intranet（企业内部网）




