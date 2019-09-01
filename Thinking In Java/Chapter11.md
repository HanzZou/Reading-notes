# 持有对象

## 11.1 泛型和类型安全的容器

不限定ArrayList的存储类型，ArrayList会把存入对象当做object来对待，取出时进行强制转型会出现运行时类型错误

## 11.2 基本概念

两个不同概念：

1. Collection：一个独立元素的序列，服从一或多条规则（List按插入顺序，Set不能有重复元素，Queue按照排队规则）
1. Map：一组成对“键值对”对象

## 11.3 添加一组元素

Array.asList()接受一个数组或逗号分隔的元素列表

Collections.addAll()接受一个Collection对象，用它来初始化自身

虽然可以用Arrays.asList()来构建，但是Collections.addAll()运行要快得多。Collections.addAll()是首选方式。

Collection.addAll()成员方法只能接受另一个collection对象作为参数，因此不如Arrays.asList()或Collections.addAll()灵活。

用Array.asList()的输出作为List的话，底层表示是数组，不能调整尺寸，add()和delete()方法都不可用。

如果不像`List<Snow> snow4 = Arrays.<Snow>asList(new Light(), new heavy());`一样**显式类型参数说明**，那么asList()方法会根据第一参数的类型来确定List的目标类型

## 11.4 容器的打印

## 11.5 List

1. 基本的ArrayList，长于随机访问元素，但是在List的中间插入和移除元素时较慢
1. LinkedList，通过带价较低的在List中间进行的插入和删除操作，提供了优化的顺序访问，但在随机访问方面相对较慢。

## 11.6 迭代器

迭代器隐化了容器的类型，使代码可以应用到不同的容器类型上。

.listIterator(n)获得一个指向索引n处的ListIterator

## 11.7 LinkedList

## 11.8 Stack

后进先出

可以封装LinkedList作为成员变量来创建自己的Stack类，也可以使用java.util.Stack

## 11.9 Set

特点是快速查找

排序的结果可以用TreeSet来存储，使用红黑树的数据结构

## 11.10 Map

HashMap不能使用基本数据类型

## 11.11 Queue

offer()将一个元素插入到队尾，peek()和element()在不移除的情况下返回队首元素，在队列为空时，peek()返回null，element()出现NoSuchElementException异常。poll()和remove()移除并返回队首。

## 11.12 Collection和Iterator

生成Iterator是将队列与消费队列的方法连接在一起耦合度最小的方式，并且与实现Collection相比，它在序列类上所施加的约束也少得多。

## 11.13 Foreach与迭代器

Arrays.asList(...)产生的list会使用底层数组作为物理实现，所以对于list的操作会影响原数组