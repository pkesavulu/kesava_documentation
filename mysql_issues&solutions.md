db issues:-
---

> Caused by: java.sql.SQLException: Access denied for user 'root'@'localhost' (using password: NO) in mysql 8.0

(or)

> Caused by: java.sql.SQLException: Access denied for user 'root'@'localhost' (using password: YES) in mysql 8.0


solution:-
---

Global Privileges:-
---

> Global privileges are administrative or apply to all databases on a given server. To assign global privileges, use ON *.* 

syntax:-
---

```
GRANT ALL ON *.* TO 'someuser'@'somehost';   // use this for all permissions
```

```
GRANT SELECT, INSERT ON *.* TO 'someuser'@'somehost';  // use this for only select and insert permissions
```

Database Privileges:-
---

> Database privileges apply to all Tables in a given database. To assign database-level privileges, use ON db_name.*

syntax:-
---
```
GRANT ALL ON mydb.* TO 'someuser'@'somehost';
```

```
GRANT SELECT, INSERT ON mydb.* TO 'someuser'@'somehost';
```

Table Privileges:-
---

> Table privileges apply to all columns in a given table. To assign table-level privileges, use ON db_name.tbl_name

```
GRANT ALL ON mydb.mytbl TO 'someuser'@'somehost';
```

```
GRANT SELECT, INSERT ON mydb.mytbl TO 'someuser'@'somehost';
```

Column Privileges:-
---

> Column privileges apply to single columns in a given table. Each privilege to be granted at the column level must be followed by the column or columns, enclosed within parentheses.

```
GRANT SELECT (col1), INSERT (col1, col2) ON mydb.mytbl TO 'someuser'@'somehost';
```


if you required more information try to follow the below links : 

https://dev.mysql.com/doc/refman/5.7/en/grant.html ,

https://dev.mysql.com/doc/refman/5.7/en/create-user.html , 

https://dev.mysql.com/doc/refman/8.0/en/show-grants.html , 

https://chartio.com/resources/tutorials/how-to-grant-all-privileges-on-a-database-in-mysql/
