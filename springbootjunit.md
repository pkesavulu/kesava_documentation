spring boot junit testing:-
---
 
use to testing our spring project

1.if you not provide application.property file saperatly then it use application.property file in src/test/resource
2. Junit test case always use inmemory database (h2,hs2bd,etc..)
3.

===

example query saved in src/main/resource as file so we should delete it first:
---
file constain this query:-
---
INSERT INTO customer(customername,landline,message,mobileno,email) VALUES('kesava','8888888','good','900088767','kesava@gmail.com');

===

Error:-
---
org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaConfiguration': 
Unsatisfied dependency expressed through constructor parameter 0; nested exception is org.springframework.beans.factory.BeanCreationException: 
Error creating bean with name 'dataSource': Invocation of init method failed; nested exception is java.lang.IllegalStateException: 
Failed to replace DataSource with an embedded database for tests. If you want an embedded database please put a supported one on the classpath or tune the replace attribute of @AutoConfigureTestDatabase.

===


packing jar:-
---

1. If you pack the class as jar after junit test to follow this steps.

	1.1.mvn clean install(it will build a jar file for you)
	1.2.mvn clean install -DskipTests (use this to skip the test cases)
	1.3.java -jar <jar file locatoin>
	
	
mocking and spying beans:-
---

use this concept to check the junit test for service layer	

