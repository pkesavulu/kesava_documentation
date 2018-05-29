# MySql Documents

- DDL(data definition language) -> create,alter,drop,rename,truncate
- DML(data manipulation language) ->select,insert,update,delete. 
- DCL(data control language)-> grant , revoke
- TCL(Transaction control language)

## DDL(Data Definition Language) 

- DDL use to define and modified the data like create command use to define data and alter,drop,rename,truncate commands use to modified the data

## DML(Data manipulatoin Language)

- DML use to retrive and manipulate the data.
- DML perfoms read-only queries of the data

## DCL(Data Control Language)

- DCL use to control the user access in a db, related to security issues.
- It allows to restrict the user from accessing data in database.

## Create database

- CREATE DATABASE databasename;

```
mysql> CREATE DATABASE EMPDB;
```
## Drop database
- DROP DATABASE DATABASE_NAME
```
mysql> drop database emp;
Query OK, 1 row affected (0.09 sec)
```

## Create table

- CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);

```
mysql> use emp;
Database changed
mysql> create table emp (id int(5),name varchar(10),city varchar(6),phno int(10)
);
Query OK, 0 rows affected (0.10 sec)
```

## Drop table

* DROP TABLE table_name;

```
mysql> drop table emp;
Query OK, 0 rows affected (0.14 sec)

mysql> show tables;
Empty set (0.00 sec)
```
## Truncate table

* The TRUNCATE TABLE statement is used to delete the data inside a table, but not the table itself.

```
mysql> TRUNCATE TABLE emp;
Query OK, 0 rows affected (0.13 sec)

mysql> show tables;
+---------------+
| Tables_in_emp |
+---------------+
| emp           |
+---------------+
1 row in set (0.00 sec)
```
## Alter Table statements

- The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

- The ALTER TABLE statement is also used to add and drop various constraints on an existing table.

> ALTER TABLE - ADD Column

- ALTER TABLE table_name
ADD column_name datatype;

```
mysql> alter table emp add column cell int(10);
Query OK, 0 rows affected (0.33 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe emp;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(5)      | YES  |     | NULL    |       |
| name  | varchar(10) | YES  |     | NULL    |       |
| city  | varchar(6)  | YES  |     | NULL    |       |
| phno  | int(10)     | YES  |     | NULL    |       |
| cell  | int(10)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
5 rows in set (0.01 sec)
```
> ALTER TABLE - DROP COLUMN

- ALTER TABLE table_name
DROP COLUMN column_name;

```
mysql> alter table emp drop column phno;
Query OK, 0 rows affected (0.13 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe emp;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(5)      | YES  |     | NULL    |       |
| name  | varchar(10) | YES  |     | NULL    |       |
| city  | varchar(6)  | YES  |     | NULL    |       |
| cell  | int(10)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
4 rows in set (0.01 sec)
```
> ALTER TABLE - ALTER/MODIFY COLUMN

- To change the data type of a column in a table, use the following syntax

- ALTER TABLE table_name
MODIFY COLUMN column_name datatype;

```
mysql> describe emp;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| id      | int(5)      | YES  |     | NULL    |       |
| name    | varchar(10) | YES  |     | NULL    |       |
| city    | varchar(6)  | YES  |     | NULL    |       |
| cell    | int(10)     | YES  |     | NULL    |       |
| address | varchar(10) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
5 rows in set (0.01 sec)

mysql> alter table emp modify column cell varchar(10);
Query OK, 0 rows affected (0.12 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe emp;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| id      | int(5)      | YES  |     | NULL    |       |
| name    | varchar(10) | YES  |     | NULL    |       |
| city    | varchar(6)  | YES  |     | NULL    |       |
| cell    | varchar(10) | YES  |     | NULL    |       |
| address | varchar(10) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
5 rows in set (0.01 sec)
```

> ALTER TABLE - CHANGE THE COLUMN NAME

* ALTER TABLE "table_name" Change "column 1" "column 2" ["Data Type"];
* ALTER TABLE "table_name" RENAME COLUMN "column 1" TO "column 2";

```
mysql> alter table emp CHANGE address addr char(10);
Query OK, 0 rows affected (0.16 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe emp;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(5)      | YES  |     | NULL    |       |
| name  | varchar(10) | YES  |     | NULL    |       |
| city  | varchar(6)  | YES  |     | NULL    |       |
| cell  | varchar(10) | YES  |     | NULL    |       |
| addr  | char(10)    | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
5 rows in set (0.01 sec)

mysql> alter table emp rename column cell to cellphone ;
Query OK, 0 rows affected (0.03 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> describe emp;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| id        | int(5)      | YES  |     | NULL    |       |
| name      | varchar(10) | YES  |     | NULL    |       |
| city      | varchar(6)  | YES  |     | NULL    |       |
| cellphone | varchar(10) | YES  |     | NULL    |       |
| addr      | char(10)    | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
5 rows in set (0.00 sec)
```


## Delete command

- Delete can use to delete the row in the table. Not deleted table structure.

> delete from emp where empno = '101';

- if u want to delete entery rows in table.

> delete from emp;

> NOTE : 
1. DELETE command use to delete the data and TRUNCATE also use to delete the data.
2. Difference between DELETE AND TRUNCATE if you use DELETE command recovery possible because it store in temporary location like recyclebin but if you use TRUNCATE recovery not possible.
3. One more difference is if you use the DELETE command to delete partially row or all the row. But if you use TRUNCATE command to delete entery rows not possible to delete partially and recovery also not possible.


## RENAME THE TABLE

- RENAME TABLE <OLD_TABLE_NAME> TO <NEW_TABLE_NAME>;

```
mysql> show tables;
+---------------+
| Tables_in_emp |
+---------------+
| emp           |
+---------------+
1 row in set (0.00 sec)

mysql> rename table emp to emp1;
Query OK, 0 rows affected (0.24 sec)

mysql> show tables;
+---------------+
| Tables_in_emp |
+---------------+
| emp1          |
+---------------+
1 row in set (0.00 sec)
```

> DCL commands to click 
> [here](https://www.youtube.com/watch?v=12ly1opuGTw)