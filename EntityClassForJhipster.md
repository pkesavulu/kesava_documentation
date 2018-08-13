entity class for db tables:-
---

1. Run ExcelToDBApp it's generated 'json files','.jh files','create tables in db and load the data'.

	> location for .jh files -> C:\git\sos\thales\excel_mining\jdlfiles
	
2. Once this process complete try to copy .jh files and past into jdlfiles directory in our jhipster project(create:jdlfiles directory manually in jhipster project)
3. open gitbash and root it our jhipster project location(ex:-/e/jhipsterProjectall/elasticsearchwithjhispter).
4. To create entity class in jhipster simply run this command(jhipster import-jdl sample1.jh smaple2.jh) it's created entity classes for db tables.

	> Ex: jhispter import-jdl employee.jh 
	
5. Once we created entity class open h2db rename the existing table name as entity class table name.

	> syntax:- ALTER TABLE <existing_table> RENAME TO <entity_class_table>;
	
	> Ex:- ALTER TABLE EMP_ RENAME TO EMP;
	
	> NOTE:- if you want entity class table name try to check here {com.elastic.jhipster.domain) in our jhipster project.
6. After table created try to add "ID" column into table.

	> syntax:- ALTER TABLE <table_name> ADD COLUMN <column_name> <data_type>;
	
	> Ex:- ALTER TABLE EMP ADD COLUMN ID INT NOT NULL AUTO_INCREMENT;
	
				(or)
				
	> ALTER TABLE EMP ADD ID INT NOT NULL AUTO_INCREMENT PRIMARY KEY;
	
	
7. Finally run the jhipster project via eclipse (or) via cmd using mvnw command (or) to run via git bash using mvn command. To chcek this project in our browser using localhost:8080.
 
