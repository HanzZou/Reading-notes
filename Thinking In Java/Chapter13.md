# 字符串

## 13.1 不可变string

String类中每一个看起来会修改String值的方法，实际上都是创建一个全新的String对象，以包含修改后的字符串内容，而最初的String对象则丝毫未动。

## 13.2 重载“+”与StringBuilder

一般的string操作，编译器会自动使用StringBuilder类来提高效率

如果字符串操作比较简单，可以信任编译器的处理，如果字符串操作复杂，应该使用StringBuilder类来提高效率

## 13.3 无意识的递归

```java
public String toString() {
    return " InfiniteRecursion address: " + this + "\n";
}
```

来打印内存地址是不正确的，`this`在进行强制类型转换时会自动调用被覆写的toString()，从而形成递归调用，打印内存地址需要Object.toString()，所以不应使用`this`，而应该是`super.toString()`。

## 13.4 String上的操作

## 13.5 格式化输出

与C语言的printf()类似的System.out.printf()和System.out.format()

格式工作由java.util.Formatter类处理，接受一个输出方向的构造参数，最常见的PrintStream()、OutputStream和File

格式修饰符的抽象语法：%[argument_index$][flags][width][.precision]conversion

## 13.6 正则表达式

不详述

## 13.7 扫描输入

可以使用BufferedReader.readLine()来逐行分析文本，也可以使用Scanner类

Scanner类的构造器可以接受File、InputStream、String或Readable对象等。进入Scanner类后，所有的输入、分词以及翻译的操作都隐藏在不同类型的next()方法中。

Scanner类并没有针对IOException添加try块，因为Scanner假设输入结束会抛出IOException，所以Scanner会把IOException吞掉，可以通过ioException()找到最近发生的异常。

Scanner也可以根据正则表达式进行分词

## 13.8 StringTokenizer