## SQL 介绍
SQL 是用于访问和处理数据库的标准的计算机语言。(Sturcture Query Language)
* SQL 指结构化查询语言
* SQL 使我们有能力访问数据库
* SQL 是一种 ANSI 的标准计算机语言

SQL 可与数据库程序协同工作，比如 MS Access、DB2、Informix、MS SQL Server、Oracle、Sybase 以及其他数据库系统。但是由于各种各样的数据库出现，导致很多不同版本的 SQL 语言，为了与 ANSI 标准相兼容，它们必须以相似的方式共同地来支持一些主要的关键词（比如 SELECT、UPDATE、DELETE、INSERT、WHERE 等等），这些就是我们要学习的SQL基础。
## SQL 的类型 
可以把 SQL 分为两个部分：数据操作语言 (DML) 和 数据定义语言 (DDL)。
* 数据查询语言（DQL: Data Query Language）
* 数据操纵语言（DML：Data Manipulation Language）
## 学习 SQL 的作用
  SQL 是一门 ANSI 的标准计算机语言，用来访问和操作数据库系统。SQL 语句用于取回和更新数据库中的数据。
  * SQL 面向数据库执行查询
  * SQL 可从数据库取回数据
  * SQL 可在数据库中插入新的记录
  * SQL 可更新数据库中的数据
  * SQL 可从数据库删除记录
  * SQL 可创建新数据库
  * SQL 可在数据库中创建新表
  * SQL 可在数据库中创建存储过程
  * SQL 可在数据库中创建视图
  * SQL 可以设置表、存储过程和视图的权限
## 数据库是什么
***DBMS分类：***
* 基于共享文件系统的DBMS
* 基于C/S的DBMS
最常见的数据库类型是关系型数据库管理系统（RDBMS）：RDBMS 是 SQL 的基础，同样也是所有现代数据库系统的基础，
<img src='D:\MarkdownFIle\SQL\QQ截图20230414171249.png'>
RDBMS 中的数据存储在被称为表（tables）的数据库对象中。表 是相关的数据项的集合，它由列和行组成。
## SQL 基础语言学习
一个数据库通常包含一个或多个表。每个表由一个名字标识（例如“客户”或者“订单”）。表包含带有数据的记录(行)。
### CREATE TABLE – 创建表
```
CREATE TABLE 表名称
(
列名称1 数据类型,
列名称2 数据类型,
列名称3 数据类型,
....
);
```
***数据类型（data_type）规定了列可容纳何种数据类型。下面的表格包含了SQL中最常用的数据类型：***
<img src='D:\MarkdownFIle\SQL\QQ截图20230414171753.png'>