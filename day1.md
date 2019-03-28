<h1 align="center">每日一句MySQL</h1>

# 1.创建/使用/删除数据库

```MySql
    create database test_python;#创建
    use test_python;#使用数据库
    drop database test_python;#删除数据库
```

# 2.创建数据表

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
        PRIMARY KEY ('column1_id')
    )ENGINE=InnoDB DEFAULT CHARSET=utf8; 
```