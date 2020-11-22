```
Hive DDL
```
```
创建数据库
CREATE DATABASE hive_test;
```
```
显示数据库
hive> show databases;
```
```
查看数据库详情
DESC DATABASE hive_test;
```
```
显示当前所在库
set hive.cli.print.current.db=true;
```
```
创建表
CREATE TABLE test(
    id int,
    name string,
    monery double
) ROW FORMAT DELIMITED FIELDS TERMINATED BY '\t';
```
```
查看表结构
desc test;
desc formatted test;
```
```
修改表名
ALTER TABLE test RENAME TO testv2;
```