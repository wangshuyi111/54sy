---
title: mysql
description: ""
date: 2026-08-14T21:32:37+08:00
lastmod: 2026-08-20T19:49:48+08:00
draft: false
slug: MuvosL-2026-003
categories:
  - study
tags:
  - study
---
# 一、创建数据库

```
CREATE DATABASE 数据库名
```

作用：创建一个数据库
```
IF NOT EXISTS
```

作用：如果数据库不存在才创建，避免重复创建报错

```
CHARACTER SET utf8mb4
```

作用：指定数据库的字符集为 utf8mb4
utf8mb4 是真正的 4 字节 UTF-8，支持所有字符（包括中文、emoji）
```
COLLATE utf8mb4
```
作用：指定排序规则
  - _ci = case insensitive（不区分大小写）
  - _unicode = 使用 Unicode 标准排序
 - 查询时 'ABC' 和 'abc' 视为相同
```
DROP DATABASE IF EXISTS
```
作用：如果数据库已存在则先删除
# 二、选择数据库
```
USE
```
作用：切换到指定数据库，后续所有操作都会在这个库里进行
# 三、创建数据表
INT
整数类型，4字节
VARCHAR
可变长度字符串，最多20个字符
无论存多少字符，只占用实际长度+1字节
COMMENT
字段注释，给字段加说明
PRIMARY KEY
唯一识别表中的每一行
不能重复，不能为NULL，一张表只能有一个主键
DECIMAL（8，2）
定点数类型，用于存储金额
8=总位数(整数+小数) 2=小数位数
为什么表名用orders而不是order？
ORDER是MySql关键字
直接用order作表名会冲突，需要加反引号，推荐用复数orders规避冲突
DATE日期类型
格式：YYYY-MM-DD
如果需要时间，用DATETIME（YYYY-MM-DD HH:MM:SS）
# 四、插入测试数据
```
INSERT INTO ... VALUES...
```
批量插入
一条INSERT插入多行，用逗号分隔：
```
INSERT INTO 表名（字段）VALUES（值1），（值2），（值3），...；
```
字符串用单引号
字符串和日期必须用单引号’张三‘，数字可以不加引号18
# 五、验证语句
查看当前数据库的所有表
```
SHOW TABLES；
```
查看表结构
DESC 表名，显示每个字段的类型、是否为空、默认值等
查看每张表的数据量
```
COUNT（* ） 统计行数
```
抽查数据
SELECT* 查询所有字段，LIMIT限制返回行数![[Pasted image 20260814184313.png]]![[Pasted image 20260814184320.png]]
# insert语句配套知识点整理
## 一、insert基本语法
```
INSERT INTO 表名 (字段1, 字段2, ...) VALUES (值1, 值2, ...);
```
## 二、数据类型的写入规则
```
字符串必须用单引号
INSERT INTO user (username, gender) VALUES ('Li Shi', 'female');
数字不需要引号
INSERT INTO user (age, status) VALUES (26, 1);
日期也用单引号
INSERT INTO orders (create_time) VALUES ('2026-04-10');
```
```
金额的正确用法
INSERT INTO goods (gname, price, stock, type) VALUES ('Jeans', 119.00, 600, 'clothing');
```
DECIMAL(8,2) 表示总共 8 位数字，小数点后保留 2 位。写入 119 或 119.00 都可以，MySQL 会自动补齐为 119.00。
```
日期的标准格式
date 2026-04-10
INSERT INTO orders (create_time) VALUES ('2026-04-10');
```
# 三、批量插入
```一次插入两个用户
INSERT INTO user (username, age, gender, phone, status) VALUES
('Wang Yiyi', 20, 'male',   '13900001111', 1),   ← 第1行数据，注意末尾逗号
('Liu Erer',  21, 'female', '13900002222', 1);    ← 最后一行，末尾用分号
```
![[Pasted image 20260817224542.png
# 四、UPDATE基本语法
update的完整结构
```
UPDATE 表名 
SET 字段1 = 新值1, 字段2 = 新值2
WHERE 条件;
```
修改一个字段，只改价格
```
UPDATE goods SET price = 3799 WHERE gname = 'Huawei Phone';
```
修改多个字段，逗号分隔
```
UPDATE user SET age = 20, status = 1 WHERE username = 'wangwu';
```
用原值参与计算
```
UPDATE goods SET price = price + 10 WHERE type = 'clothing';
```
直接赋值
```
UPDATE goods SET stock = 500 WHERE stock < 300; 
UPDATE goods SET price = 3799 WHERE gname = 'Huawei Phone';
```
IN关键字
```
-- 假设要把所有 digital 和 clothing 分类改价
UPDATE goods SET price = price * 0.9
WHERE type IN ('digital', 'clothing');
```
SELECT验证
先看要改哪些
```
SELECT * FROM user WHERE username = 'wangwu';
```
再update
```
UPDATE user SET age = 20, status = 1 WHERE username = 'wangwu';
```
再SELECT确认改对了
```
SELECT * FROM user WHERE username = 'wangwu';
```
![[Pasted image 20260820195412.png]]