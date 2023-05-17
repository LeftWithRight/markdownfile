## DDL(data definition language);定义数据库对象（数据库、表、字段）
* 创建
  ```
  create database 数据库名 （default charset utf8mb4 collate 排序规则）；  //括号内为可选
  ```

* 使用 use





## DML（Data manuplation language）;shujuku 操作语言
* 添加数据
  ```
  insert into 表名 （字段1，字段2）values(值1，值2)  //给指定字段添加数据
  insert into 表名 values (值1，值2)；    //给全部字段添加数据
  insert into 表名(字段1，字段2...) values (值1，值2)（值1，值2...）   //批量添加数据
  insert into jdbc_learn.customers(id,name,email,birth,photo) values(20,"王鸥","wo@163.com","1998-3-11", null);
  insert into jdbc_learn.customers values(21,"王鸥","wo@163.com","1998-3-11", null);

  ```
* 修改数据   update
  ```
  update 表名 set 字段名1=值1，字段名2=值2，***【where 条件】；  //不带where条件则修改整张表的信息
* 删除
```
DDELETE form 表名 where 条件   //删除数据；此处删除整条数据
drop database //数据库名
```
// delelte 语句不能删除某一个字段的值，（可以使用update语句置为null，）
* 修改表结构。
 使用ALTER TABLE语句
 ```
 ALTER TABLE users ADD COLUMN address VARCHAR(255);  //在users表中添加一个新列address，数据类型为VARCHAR(255)
```
如果你想为新列指定默认值，可以在ADD COLUMN子句中使用DEFAULT关键字，
```
ALTER TABLE users ADD COLUMN age INT DEFAULT 18;  //将在users表中添加一个名为age的新列，数据类型为INT，默认值为18。
```
## DQL(data query language)数据查询语言，
* 聚合函数  //将一列数据作为一个整体，进行纵向计算；
  常见聚合函数：
  count //统计数量； max   //最大值；min  //最小值； avg   //平均值； sum  //求和；
  ```
  select count(*) from jdbc_learn.customers;  //统计员工个数
  select count(id) from jdbc_learn.customers; //同上  
   ```
   1. null值不参与聚合计算；

* 分组查询 （group by）
  ```
  select 字段列表 from 表名 【where 条件】 group by 分组字段名 【having 分组后过滤条件】   //【】内部为可选
   select gender, count(*) from emp group by gender;   // 根据性别分组，统计男性员工和女性员工的数量；
   select  gender, avg(age) from emp group by gender;  //根据性别分组，统计男性员工和女性员工的平均年龄；
   select workaddress, count(*) from emp where age < 45 group by workaddress having count(*) >=3 ;  //查询年龄小于45的员工，并根据工作地址分组，获取员工数量大于等于3的工作地址；
  ```
  执行顺序：where > 聚合函数 > having;
  分组之后，查询的字段一般为聚合函数和分组字段，查询其他字段没有意义；

* 排序查询
  ```
 select 字段列表 from 表名 order by 字段1 排序方式1，字段2 排序方式2；
  
 ```
 asc 升序；dsc： 降序；
 如果是多字段排序，当第一个字段值相同时，才会根据第二个字段进行排序；
## DCL(data control language)





## 偏记忆与理解
1. where与having区别：
   执行时机不同：where是分组之前进行过滤，不满足where条件，不参与分组；erhaving是分组之后对结果进行过滤。
   判断条件不同：where不能对聚合函数进行判断，而having可以；