# spring boot:-
---

## Repository:- 
---

use this repository to impletement basic operation with out writing extra code manually from scrach, They provide boilerplate code all we just extend that repository
with some new repository and use it.

### spring data comman:-
---

1.repository -> basic repositry to impletement normally.
2.crudrepository -> child of repository and it's use to do some curd operations like create,delete,deleteall,find,findall,updated.
3.pagingandsortingrepository -> child of curdrepository and it have 2 methods like one is findall(Sort sort),findall(Pagination pagination).

### spring data jpa:-
---

4.jparepository-> it's is child of "pagingandsortingrepository" 
use this repository to do some curd and extra activities also.


### custom queries:-
---

1.create database queries from method names(List<people> findByName(String name))
2.@Named query and @NamedNativeQueries
3.@query annotation -new edition (it's not in hibernate)
 

 