<h1 align="center">每日一句MySQL</h1>

# 1.创建/使用/删除数据库

```sql
    create database test_python;-- 创建
    use test_python;-- 使用数据库
    drop database test_python;-- 删除数据库
```

# 2.创建/删除数据表
新增数据表:

```sql
    create table table_name (
        `column1_id` INT UNSIGNED AUTO_INCREMENT,
        `column1_name` VARCHAR(40) NOT NULL,
        PRIMARY KEY ('column1_id')
    )ENGINE=InnoDB DEFAULT CHARSET=utf8;
```
或则：

```sql
    create table if not exists `table_name`(
       `column1_id` INT UNSIGNED AUTO_INCREMENT,
        `column1_name` VARCHAR(40) NOT NULL,
        `column1_age` INT UNSIGNED NOT NULL,
        PRIMARY KEY ('column1_id')
    )ENGINE=InnoDB DEFAULT CHARSET=utf8; 
```
删除数据表：

```sql
    drop table table_name
```

# 3.插入数据

```sql
    insert into table_name (column1_name) values ("test")
```
如果所有列都要添加数据，可以如下所示：

```sql
    insert inot table_name values (0,"inory",19)
```
第一列如果没有设置主键自增（PRINARY KEY AUTO_INCREMENT）的话添加第一列数据比较容易错乱，要不断的查询表看数据。
如果添加过主键自增（PRINARY KEY AUTO_INCREMENT）第一列在增加数据的时候，可以写为0或者null，这样添加数据可以自增， 从而可以添加全部数据，而不用特意规定那几列添加数据。

# 4.查询语句

```sql
    -- 基础查询
    select column_age,column_name from table_name
    /*加入where*/
    select column_age from table_name where column_age>10
```

# 5.数据更新/删除

```sql
    /*修改数据,更新数据表中指定行的数据时，where很有用,不加的时候更新所有数据的对应字段*/
    update table_name set field1=new-value1,field2=new-value2 [where clause]
    /*删除数据，同上，不添加where语句时，删除表中所有数据*/
    delete from table_name [where clause]
```

# 6.模糊查询

```sql
    /*like字句使用'%'表示任意字符，如果没用，则跟'='效果一样
    通常情况下，‘%’与like一同使用*/
    selct field from table_name where fieldn like condition
```

# 7.UNION操作字符

```sql
    select expression from tables [where conditions] union [ALL | DISTINCT] select expression from tables [where conditions]
```
- expression:要检索的列
- tables：要检索的数据表
- where conditions:可选，检索条件
- DISTINCT: 可选，删除结果集合中重复的数据。默认情况下UNION操作符已经删除了重复数据.
- ALL：可选，返回所有结果集，包含重复数据