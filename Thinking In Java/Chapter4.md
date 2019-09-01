# 控制执行流程

## 4.1 true和false

数字不能作为布尔值（虽然在C和C++里被允许)

## 4.2 if-else

## 4.3 迭代

while、do-while、for

## 4.4 Foreach语法

## 4.5 return

## 4.6 break和continue

## 4.7 臭名昭著的goto

编译器生成的汇编代码中包含许多跳转

continue和break的标签规则：

+ 一般的continue会退回最内层循环的开头，并继续执行
+ 带标签的continue会到达标签的位置，并重新进入紧接在那个标签后面的循环
+ 一般的break会中断并跳出当前循环
+ 带标签的break会中断并跳出标签所指的循环

## 4.8 switch

字符串和浮点数作为选择因子是不会工作的，需要使用int或char那样的整数值

