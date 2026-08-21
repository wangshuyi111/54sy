---
title: Java
description: ""
date: 2026-07-12T22:14:50+08:00
lastmod: 2026-08-21T17:16:40+08:00
draft: false
slug: 54sy-2026-001
categories:
  - study
tags:
  - exercise
  - java基础
---
# 一、Java基础语法
## 1.Java程序基本结构
### 1.1 class
class是程序的基本单位，是一个关键字，后面跟着的是类名Hello，类名必须以英文字母开头，后接字母，数字和下划线的组合。
```java
public class Hello { // 类名是Hello
    // ...
} // class定义结束
```
1.2public是访问修饰符，表示该class是公开的，方法名是main，返回值是void，表示没有任何返回值。public除了修饰class外，也可以修饰方法，而关键字static是另一个修饰符，表示静态方法，Java入口程序规定的方法必须是静态方法，方法名必须为main，括号内的参数必须是String数组。
```java
public class Hello {
    public static void main(String[] args) { // 方法名是main
        // 方法代码...
    } // 方法定义结束
}
```

## 2.变量
### 2.1基本数据类型
整数类型：byte，short，int，long
浮点数类型：float，double
字符类型：char
布尔类型：boolean
引用类型：string
常量：在前面加final
## 3.整数运算
### 3.1自增和自减
++：对整数加一
--：对整数减一
注意：++n表示先加一在引用n，n++表示先引用再加一
### 3.2位运算
3.2.1与运算：必须两个数同时为1，结果才为1
```
n = 0 & 0; // 0
n = 0 & 1; // 0
n = 1 & 0; // 0
n = 1 & 1; // 1
```
3.2.2或运算：只要任意一个为1，结果就为1
```
n = 0 | 0; // 0
n = 0 | 1; // 1
n = 1 | 0; // 1
n = 1 | 1; // 1
```
3.2.3非运算：0和1互换
```
n = ~0; // 1
n = ~1; // 0
```
3.2.4异或运算：如果两个数不同，结果为1，否则为0
```
n = 0 ^ 0; // 0
n = 0 ^ 1; // 1
n = 1 ^ 0; // 1
n = 1 ^ 1; // 0
```
### 3.3运算优先级
- `()`
- `!` `~` `++` `--`
- `*` `/` `%`
- `+` `-`
- `<<` `>>` `>>>`
- `&`
- `|`
- `+=` `-=` `*=` `/=`
## 4.布尔运算
- 比较运算符：`>`，`>=`，`<`，`<=`，`==`，`!=`
- 与运算 `&&`
- 或运算 `||`
- 非运算 `!`
### 4.1三元运算符，b？x：y
首先计算b，若b为true，则只计算x，否则，只计算y
## 5.输入和输出
### 5.1格式化输出printf
| 占位符 | 说明               |
| --- | ---------------- |
| %d  | 格式化输出整数          |
| %x  | 格式化输出十六进制整数      |
| %f  | 格式化输出浮点数         |
| %e  | 格式化输出科学计数法表示的浮点数 |
| %s  | 格式化字符串           |
### 5.2if条件判断
```java
// 从小到大依次判断：
if (条件) {
    // ...
} else if (条件) {
    // ...
} else {
    // ...
}
```
### 5.3switch多重选择
```java
switch (option) {
case 3:
    ...
    break;
case 2:
    ...
    break;
case 1:
    ...
    break;
} 
```
计算结果必须是整型、字符串或枚举类型。
### 5.4while循环
```java
while (条件表达式) {
    循环语句
}
```
先判断循环条件是否满足，再执行循环语句
循环可能一次都不执行
### 5.5do while循环
```java
do {
    执行循环语句
} while (条件表达式);
```
先执行循环，再判断条件
循环会至少执行一次
### 5.6for循环
```java
for (初始条件; 循环检测条件; 循环后更新计数器) {
    // 执行语句
}
```
### 5.7break和continue
break语句通常都是配合if语句使用，break语句总是跳出自己所在的那一层循环
conntinue语句可以提前结束本次循环，通常配合if，在满足条件时提前结束本次循环
# 6.数组
## 6.1遍历数组
遍历数组可以用for循环
```java
// 遍历数组
public class Main {
    public static void main(String[] args) {
        int[] ns = { 1, 4, 9, 16, 25 };
        for (int i=0; i<ns.length; i++) {
            int n = ns[i];
            System.out.println(n);
        }
    }
}
```
![[Pasted image 20260816173926.png|334]]

还有一种是使用for each循环，直接迭代数组的每个元素
```java
// 遍历数组
public class Main {
    public static void main(String[] args) {
        int[] ns = { 1, 4, 9, 16, 25 };
        for (int n : ns) {
            System.out.println(n);
        }
    }
}
```
![[Pasted image 20260816174505.png]]
## 6.2数组排序
6.2.1冒泡排序
特点：每一轮循环后，最大的一个数被交换到末尾，因此，下一轮循环就可以“刨除”最后的数，每一轮循环都比上一轮循环的结束位置靠前一位。
```java
// 冒泡排序
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] ns = { 28, 12, 89, 73, 65, 18, 96, 50, 8, 36 };
        // 排序前:
        System.out.println(Arrays.toString(ns));
        for (int i = 0; i < ns.length - 1; i++) {
            for (int j = 0; j < ns.length - i - 1; j++) {
                if (ns[j] > ns[j+1]) {
                    // 交换ns[j]和ns[j+1]:
                    int tmp = ns[j];
                    ns[j] = ns[j+1];
                    ns[j+1] = tmp;
                }
            }
        }
        // 排序后:
        System.out.println(Arrays.toString(ns));
    }
}
```
## 6.3多维数组
二维数组是数组的数组
三维数组是二维数组的数组
## 6.4 命令行参数
命令行参数类型是`String[]`数组；
命令行参数由JVM接收用户输入并传给`main`方法；
# 二、面向对象
## 1.方法
### 1.1private方法
一个class可以包含多个field，例如
```java
class Person {
    public String name;
    public int age;
}
```
为了避免外部代码直接去访问field，我们可以用private修饰field，拒绝外部访问
```java
class Person {
    private String name;
    private int age;
}
```
### 1.2this变量
this始终指向当前实例，通过this.field就可以访问当前实例的字段。
如果没有命名冲突，可以省略this
```java
class Person {
    private String name;

    public String getName() {
        return name; // 相当于this.name
    }
}
```
如果有局部变量和字段重名，那么局部变量优先级更高，就必须加上this
```
class Person {
    private String name;

    public void setName(String name) {
        this.name = name; // 前面的this不可少，少了就变成局部变量name了
    }
}
```
### 1.3方法参数
方法参数用于接收传递给方法的变量值。调用方法时，必须严格按照参数的定义传递。
```java
class Person {
    ...
    public void setNameAndAge(String name, int age) {
        ...
    }
}
```