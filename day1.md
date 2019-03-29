<h1 align="center">每日一句MySQL</h1>

# 1.创建/使用/删除数据库

```MySql
    create database test_python;#创建
    use test_python;#使用数据库
    drop database test_python;#删除数据库
```

# 2.创建/删除数据表
新增数据表:

```bash
    create table table_name (
        `column1_id` INT UNSIGNED AUTO_INCREMENT,
        `column1_name` VARCHAR(40) NOT NULL,
        PRIMARY KEY ('column1_id')
    )ENGINE=InnoDB DEFAULT CHARSET=utf8;
```
或则：

```bash
    create table if not exists `table_name`(
       `column1_id` INT UNSIGNED AUTO_INCREMENT,
        `column1_name` VARCHAR(40) NOT NULL,
        `column1_age` INT UNSIGNED NOT NULL,
        PRIMARY KEY ('column1_id')
    )ENGINE=InnoDB DEFAULT CHARSET=utf8; 
```
删除数据表：

```bash
    drop table table_name
```

# 3.插入数据

```bash
    insert into table_name (column1_name) values ("test")
```
如果所有列都要添加数据，可以如下所示：

```bash
    insert inot table_name values (0,"inory",19)
```
第一列如果没有设置主键自增（PRINARY KEY AUTO_INCREMENT）的话添加第一列数据比较容易错乱，要不断的查询表看数据。
如果添加过主键自增（PRINARY KEY AUTO_INCREMENT）第一列在增加数据的时候，可以写为0或者null，这样添加数据可以自增， 从而可以添加全部数据，而不用特意规定那几列添加数据。
