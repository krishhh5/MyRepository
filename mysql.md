#  mysql
###### 创建数据库
- CREATE DATABASE 数据库名;
###### 删除数据库
- drop database <数据库名>;
###### 选择数据库
- use RUNOOB;
##### 数据类型
###### 数值类型
- tinyint
- smallint
- mediumint
- int/integer
- bigint
- float
- double
- decimal
 ###### 日期和时间类型
- date yyyy-mm-dd
- time hh:mm:ss
- year yyyy
- timestamp yyyyymmdd hhmmss
###### 字符串类型
- char 
- varchar
- tinyblob
- tinytext
- blob
- text
- mediumblob
- mediumtext
- longblob
- longtext
- 建表
- create table tableName
-
```
( 
  字段1 数据类型 AUTO_INCREMENT,
  字段2 数据类型,
   ...
);
```
###### 删表
- DROP TABLE table_name ;
###### 删除表内数据
- delete from 表名 where 删除条件;
###### 清空表内数据(保留表结构)
- truncate table 表名;
###### 释放表空间(delete后使用)
optimize table tableName;
###### 插入数据
IN
`
```
``
SERT INTO table_name ( field1, field2,...fieldN )
                       VALUES
                       ( value1, value2,...val
ueN );
```
###### 读取数据表
- select * from runoob_tbl;
###### 查询数据
-
```
SELECT column_name,column_name
FROM table_name
[WHERE Clause]
[LIMIT N][ OFFSET M]
```
###### 修改数据

```
UPDATE table_name
SET field1=new-value1, field2=new-value2
[WHERE Clause]
```
##### 给已存在的列设置主键
1. alter table tableName add primary key (columName);
1. alter table tablename modify id int(11)  auto_increment;
###### 模糊搜索
- select * from cinema where cAddress like"+cAddress(字符串)
- select * from hs_user where ID like '%123%'(数字)
