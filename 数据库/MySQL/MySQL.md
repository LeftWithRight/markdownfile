# MySQL
```MySQL -V //查看当前运行的版本；   ```   
## 启动，
1. 从计算机管理找到服务名称——>以管理员身份打开命令窗口——>net start <服务名称>
2. 同理，停止服务：——>net stop <服务名称>
## 登录
方式一：MySQL自带客户端
MySQL command line Client
只能以root身份进入
方式二：命令行   (要以管理员身份运行命令提示符)
mysql -u<username> -p<password>
***连接其他的数据库（非主机）***
mysql -h<主机名（ip address> -P<端口号> -u<user> -p<password>
## 选择数据库
use <schema>;
show database;  //展示现有的数据库；
show tables;  //展示表
select database();  //展示正在使用的数据库
## 创建表
```
create table students(
    id int,
    name varchar(10),
);
```
**针对这个表的操作**
```
desc students;   //descrip  描述信息
```
```
select * from students;  //可以用于查看表的内容
```
```
insert into students value(1,"andy");   //插入数据
```
```
update students set name="jeck" where id=1; //修改数据
```
```
delete from students where id=1;   //删除
```
```
alter table students add column tel varchar(11);    //添加字段
```
```
drop tables <tables>;   //
```
```
exit;
```
## 不区分大小写
**库名，表名，字段名，建议大写；其他小写**
## 注释
* #符号，
* --后空加一个格
* /**/

##  query
### 基础查询
  select 查询列表 from 表名  #特点： 查询的数据集为一个虚拟表；
  select 后面可以跟的查询列表可以有多个组成部分，中间用逗号隔开；  #select 字段1，字段2，表达式 from 表；

  ***查询列表可以是： 字段、表达式、常量、函数***
  1. 查询常量
   ```
   select 100;
   ```
  2. 查询表达式
   ```
   select 100%3;
   ```
  3. 查询单个字段
  ```
   select 'last_name' from 'emploees';
   ```
  4.  查询函数
   ```
   select databases();
   select version();
   select user();
   ```
   5. 起别名
    * select user() as 用户名；  #双引号可加可不加，对于别名中间内部存在空格的需要加引号； 
    * 使用空格 select user() 别名 from tableName;
   6. sql中的拼接  (CONCAT)
      ***java中的 + 符号：***
      * 加法运算符
      * 连接符
        字符串 + 其他类型，
      ***sql中的+符号：***  其中一个操作数为字符型，会将字符型数据强制转换为数值型，如无法转换，则为0； null+其他——>null
      ***使用concat***函数
      ```
      select concat(first_name, last_name) as "姓名" from emploees;
      ```
      concat函数遇到值为null时，常结合**ifnull**使用
      ```
      select concat(employee_id,',',first_name,',','last_name',',',ifnulll(commission_pct,'') as "output" from employees;
      ```
    7. distinct的使用   #查询员工涉及到的部分编号有哪些  (重复部分步不显示)
       ```
       select distinct department_id from employees;
    8. 查看表的结构
      ```
       desc employees;                       #describe
       show columns from employees;
       ```
### 进阶查询
  ```
  /*
  语法：
  select 查询列表
  from 表名
  where 筛选条件
  */
  ```
  1. 按关系表达式筛选
    关系运算符： <, >, =, !=,<>(mysql中的不等于)
  2. 逻辑表达式筛选
        and or not 
  3. **模糊查询**  :
    like,  in, between and,is null,  not(),
    * like   
       /*
       **一般和通配符搭配使用，对字符型数据进行部分匹配查询**
       常见通配符：  任意单个字符串，任意多个字符串
       同理 not like
       */
       ```
       #案例：查询姓名中包含字符a的员工信息
       select * 
       from empolyees
       where last_name like '%a%';
       #查询姓名中包含第一个字符为e的员工信息
       select * from employees where last_name like 'e%';
       #查询姓名中包含最后一个字符为e的员工信息
       select * from employees where last_name like '%e';
       #查询姓名中包含第三个字符为x的员工信息
       select * from employees where last_name like '__x%'   #x前面设置了两个下划线
       #查询姓名中第二个字符为_的字符：
       select * from employees where last_name like'_$_%' escape $;
       select * from employees where last_name like '_\_%'
       ```
    * in 
     /*
     **查询某字段的值是否属于特定的列表之内**
     in(常量值1，常量值2，常量值3，...)
     in/not in
     */
     #案例：查询部分编号是30/50/90的员工名、部门编号：
     select last_name,department_id from employees where department_id in(30,50,90)
     select last_name,department_id from employees where department_id=30 or department_id=60 or department_id=90
     #案例查询工种编号不是sh_clerk或it_prog的员工信息：
     select * from employees where job_id not in ('sh_clerk','it_prog');
     select * from employees where not(job_id='sh_clerk' or job_id='it_prog'); 
     * between and
     /*
     **功能：判断某个字段的值是否介于xx之间**
     between and/not between and
     */
     案例1：查询部门编号是30-90之间的部门编号、员工姓名：
     select department_id,lastname from employees where department_id between 30 and 90;
     select department_id,lastname from employees where department_id >= 30 and department <= 90;
     #案例2：查询年薪不是100000-200000之间的员工姓名、工资、年薪
     select last_name,salary,salary,salary*(1+ifnull(commission_pct,0)) 年薪 from employees where salary*(1+ifnull(commission_pct,0)) not bwtween 100000 and 200000;
     * is null/is not null
      #案例：查询没有奖金的员工信息
      select * from employees where salary_pct is null;
       **=只能判断普通值，而IS只能判断null值；<=>安全等于，既能判断普通内容，又能判断null值**
    
  ### 进阶查询：排序查询
  /*    语法：
  select 查询列表
  from  表名
  where 筛选条件
  order by  排序查询
  **特点：**
  * 排序列表可以是单个字段，多个字段、表达式、函数、列表、以及以上的组合；
  * 升序：，通过asc(默认)   (ascending)
  * 降序：通过 desc,
  */
  #1.按单个字段排序
  #案例1：将员工编号>120的员工信息进行工资的升序
  select * from employees where employee_id > 120 order by salary asc;
  #2.按表达式排序
  #对有奖金的员工，按年薪降序
  select *,salary*12*(1+ifnull(commission_pct,0)) 年薪 from myemployees.employees where commission_pct is not null order by salary*12*(1+ifnull(commission_pct,0)) desc;
  select *,salary*12*(1+ifnull(commission_pct,0)) 年薪 from myemployees.employees where commission_pct is not null order by 年薪 desc;
  #3.按函数的结果进行排序
   select last_name,length(last_name) from employees order by length(last_name)
   #4.按多个字段排序
   #案例：查询员工的姓名，工资，部门编号，先按工资升序，再按部分编号降序；
   select last_name,salary,department_id from employees order by salary asc, department_id desc;

## 常见函数
1. 定义函数
2. 调用函数
* 字符函数
* 数学函数
* 日期函数
* 流程控制函数
### 字符函数
* concat 拼接字符
  ```
  select concat('hello', first_name, last_name) 备注 from employees;
  ```
* length 获取字节长度
  ```
  select length('hello，郭襄')； #utf_8一个中文三个字节
  ```
* char_length 获取字符长度
  ```
  select char_length('hello,郭襄')；  #字符长度是字符个数；
  ```
* substring 截取字符
  ```
  substr(str,起始索引，截取字符长度)
  substr(str,起始索引)
  select substr('张三丰爱上郭襄'，0，3)  #SQL中起始索引为1；
  ```
* instr 获取字符第一次出现的索引
  ```
  select instr('三打白骨精'，'白骨精')；
  ```
* trim去前后空格
  ```
  select trim('  虚 竹  ') as a;
  select trim('x' from 'xxxxxxx虚竹xxxxxxxxxx') as a;
  ```
* lpad/rpad    左填充/右填充
  ```
  select lpad('木婉清'，10，'a');
  ```
* upper/lower  变大写
* strcmp 比较两个字符大小
   ```
   select strcmp('abc','aaa');    #前面大结果为1；前面小，结果为-1；相等为0；
   ```
* left/right       截取字符
  ```
  select 
 
























## 多次理解的知识
表中的列又称为i”字段“，相当于java中的属性；表中的每一行数据，相当于java中的”对象“；
