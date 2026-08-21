---
title: "260815"
description: ""
date: 2026-08-16T20:26:13+08:00
lastmod: 2026-08-21T15:26:32+08:00
draft: false
slug: 54sy-2026-005
categories:
  - log
tags:
---
1.今天学习了switch多重选择的基本语句，
```
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
switch的计算结果必须是整型、字符串或枚举类型
2.
```
```while (条件表达式) {
    循环语句
}
```
先判断循环条件是否满足，再执行循环语句
循环可能一次都不执行
3.do while循环
```
do {
    执行循环语句
} while (条件表达式);
```
先执行循环，再判断条件
循环会至少执行一次
4.for循环
```
for (初始条件; 循环检测条件; 循环后更新计数器) {
    // 执行语句
}
```
5.break和continue
break语句通常都是配合if语句使用，break语句总是跳出自己所在的那一层循环
conntinue语句可以提前结束本次循环，通常配合if，在满足条件时提前结束本次循环