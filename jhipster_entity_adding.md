# entity creation process in jhipster
---


1.To create entity use the this command  
	
	jhipster entity ename_of_entity
	
```
	Ex:-jhipster enity emp
	
```
	

2.To add fields names and relationships for each entity fields.(Note:- entity names start with lowercas)

3. finally override all.

4. if to add are remove the existing entity field names to follow the below step

		jhipster entity existing_entity_name
		
```
	Ex:-jhipster enity emp
	
```
	
	4.1 choose the option regenerate entity(or) remove entity field names(or) add entity field names

	4.2 finally override all.
	
	
Error:-
---

```
2018-07-07 07:36:12.136 ERROR 8644 --- [cker-Executor-1] i.f.p.c.liquibase.AsyncSpringLiquibase   : Liquibase could not start correctly, your database is NOT ready: Validation Failed:
     1 change sets check sum
          classpath:config/liquibase/changelog/20161205191514_added_entity_Person.xml::20180723060741-1::jhipster is 7:b92d6a054bbdf952b81fa58376bd6a66 now: 7:bbbc1b54eb5939468bafd879e0fd71c8
```		  

		  
If you got error like this to follow below step in db here we are using mysql so i goto open mysql.
---

1. switch the mysql into safemode

2. SET SQL_SAFE_UPDATES=0;(it's switch into safemode)

3. select * from databasechangelog;

4. update databasechangelog set  MD5SUM = '7:bbbc1b54eb5939468bafd879e0fd71c8' where id = '20180723060741-1'

5. SET SQL_SAFE_UPDATES=1;(close the safemode)

