sqoop:-
---

Sqoop is use to import and export data from rdbms to hadoop and hadoop to rdbms

import table from rdbms to hadoop:-
---

sqoop import \
--connect jdbc:mysql://<host>/<db> \
--username root \
--password root \
--table emp \
--column id,name
--m 4 \
--target-dir <path> \
--incremental append \
--check-column id \
-last value 1204


(or)

sqoop import \
--connect jdbc:mysq:\\<host>\<db> \
--username root \
--password root \
--where "city='chennai'" \
--target-dir '/user/hive/mydir' \
--m 1 \


export table from hdfs to rdbms:-
---

sqoop export \
--connect jdbc:mysql://<host>/<db> \
--username root \
--password root \
--table emp \
--input-field-terminated-by "\t" \
--export-dir <path> 


sqoop jobs:-
---

below is the command for creating sqoop job


sqoop job \
--import \
--connect jdbc:mysql://<host>/<db> \
--username root \
--password root \
--table emp \
--m 4 \
--target-dir <path> \
--column id,name \
--incremental append \
--check-column id \
-last value 209

To view list of sqoop jobs:-
---
sqoop job --list

To execute:-
---
sqoop job --exec <name of the job>

To show jobs:-
---
sqoop job --show

Only few table is required then we use exclude command to leave those tables:-
---

sqoop import-all-tables\
 --connect jdbc:mysql://localhost/sqoop \
 --username root \
 --password hadoop \
 --target-dir '/Sqoop21/AllTables' \
 --exclude-tables <table1>,<tables2>
 
To import all tables and store into specified directory in hdfs wharehouse folder:-
---

sqoop import-all-tables \
--connect jdbc:mysql://localhost/sqoop \
--username root \
--password hadoop \
--warehouse-dir '/Sqoop'

Eval(use to execute sql querys in to sqoop):-
---
sqoop eval \
--connect jdbc:mysql:\\<host>\<db>
--username root
--table emp
--query "select * from emp where loc='chennai' "













































