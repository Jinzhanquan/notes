# mysql基本语法
## 连接数据库
```
语法：MYSQL -U ROOT -P
示例：
[root@bogon ~]# mysql -u root -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 21
Server version: 5.7.23 MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 

```
## 数据库

* 创建数据库
```
语法：CREATE DATABDSE 数据库名；
示例：
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| RUNOOB             |
| mysql              |
| performance_schema |
| sys                |
| task               |
+--------------------+
6 rows in set (0.00 sec)

mysql> create database java;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| RUNOOB             |
| java               |
| mysql              |
| performance_schema |
| sys                |
| task               |
+--------------------+
7 rows in set (0.00 sec)
```
* 删除数据库
```
语法：DROP DATABASE 数据库名
示例：
+--------------------+
| Database           |
+--------------------+
| information_schema |
| RUNOOB             |
| java               |
| mysql              |
| performance_schema |
| sys                |
| task               |
+--------------------+
7 rows in set (0.00 sec)

mysql> drop database java;
Query OK, 0 rows affected (0.00 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| RUNOOB             |
| mysql              |
| performance_schema |
| sys                |
| task               |
+--------------------+
6 rows in set (0.00 sec)

```

* 列出系统中所有数据库列表
``` 
语法：SHOW DATABASES；
示例：
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| RUNOOB             |
| java               |
| mysql              |
| performance_schema |
| sys                |
| task               |
+--------------------+
7 rows in set (0.00 sec)
```
## 数据表

* 创建数据表
**创建数据表需要以下信息：表名，表字段名，定义每个字段。**
```
语法:CREATE TABLE IF NOT EXISTS 表名(IF NOT EXISTS可加可不加，用来判断所创建的表是否存在) 
示例：
 mysql> CREATE TABLE IF NOT EXISTS tasks (
    ->     task_id INT(11) AUTO_INCREMENT,
    ->     subject VARCHAR(45) DEFAULT NULL,
    ->     start_date DATE DEFAULT NULL,
    ->     end_date DATE DEFAULT NULL,
    ->     description VARCHAR(200) DEFAULT NULL,
    ->     PRIMARY KEY (task_id)
    -> )ENGINE=InnoDB 
Query OK, 0 rows affected, 1 warning (0.00 sec)
```
* 显示数据表
**显示数据表的属性，属性类型，主键信息 ，是否为 NULL，默认值等其他信息。**
```
语法：SHOW COLUMNS FROM 表名
示例： mysql> show columns from tasks;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| task_id     | int(11)      | NO   | PRI | NULL    | auto_increment |
| subject     | varchar(45)  | YES  |     | NULL    |                |
| start_date  | date         | YES  |     | NULL    |                |
| end_date    | date         | YES  |     | NULL    |                |
| description | varchar(200) | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)
```
* 删除数据表
```
语法：DROP TABLE 表名
示例：
mysql> show tables;
+----------------+
| Tables_in_task |
+----------------+
| class          |
| tasks          |
+----------------+
2 rows in set (0.00 sec)
mysql> drop table class;
Query OK, 0 rows affected (0.01 sec)
mysql> show tables;
+----------------+
| Tables_in_task |
+----------------+
| tasks          |
+----------------+
1 row in set (0.00 sec)
```

