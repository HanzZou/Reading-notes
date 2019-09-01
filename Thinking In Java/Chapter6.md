# 访问控制权限

# 6.1 包:库单元

每个编译单元（Java源码文件）都只能有一个public类，且要求与源文件同名。如果该编译单元中还有额外的类，那么在包之外的世界是无法看到这个类的，这是因为它们不是public类，而且它们主要用来为主public类提供支持。

## 6.2 Java访问权限修饰词

private可用于控制创建对象，把构造器设为private还可以阻碍对这类的继承

protected将成员变量的访问权赋予其他包的派生类而不是所有类，同时也具有包访问权限

## 6.3 接口和实现

## 6.4 类的访问权限