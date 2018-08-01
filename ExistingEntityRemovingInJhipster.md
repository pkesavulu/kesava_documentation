How to Remove the Existing Entity in JHipster:-
---

You should delete the following:
---

```
rm -rf src/main/resources/config/liquibase/changelog/XXX_added_entity_YourEntity.xml
rm -rf src/main/java/com/radsphere/jeces/domain/YourEntity.java
rm -rf src/main/java/com/radsphere/jeces/repository/YourEntityRepository.java
rm -rf src/main/java/com/radsphere/jeces/web/rest/YourEntityResource.java 
rm -rf src/main/webapp/scripts/app/entities/YourEntity/YourEntitys.html
rm -rf src/main/webapp/scripts/app/entities/YourEntity/YourEntity-detail.html
rm -rf src/main/webapp/scripts/app/entities/YourEntity/YourEntity.js
rm -rf src/main/webapp/scripts/app/entities/YourEntity/YourEntity.controller.js
rm -rf src/main/webapp/scripts/app/entities/YourEntity/YourEntity-detail.controller.js
rm -rf src/main/webapp/scripts/components/entities/YourEntity/YourEntity.service.js
rm -rf src/test/java/com/radsphere/jeces/web/rest/YourEntityResourceTest.java
rm -rf src/main/webapp/i18n/en/YourEntity.json
rm -rf src/main/webapp/i18n/fr/YourEntity.json   

```

    
And remove the reference from config/liquibase/master.xml:
---

```

<?xml version="1.0" encoding="utf-8"?>
<databaseChangeLog
xmlns="http://www.liquibase.org/xml/ns/dbchangelog"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://www.liquibase.org/xml/ns/dbchangelog http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-3.1.xsd">

<include file="classpath:config/liquibase/changelog/00000000000000_initial_schema.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307175923_added_entity_Company.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307180142_added_entity_UserTypeRecruiter.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307180338_added_entity_UserTypeCandidate.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307180448_added_entity_QuestionType.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307180612_added_entity_Question.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307180849_added_entity_Answer.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307181033_added_entity_CandidateAnswer.xml" relativeToChangelogFile="false"/>
<!--<include file="classpath:config/liquibase/changelog/20150307181249_added_entity_your_removed_entity.xml" relativeToChangelogFile="false"/>-->
<include file="classpath:config/liquibase/changelog/20150307182736_added_entity_ExamTemplate.xml" relativeToChangelogFile="false"/>
<include file="classpath:config/liquibase/changelog/20150307182950_added_entity_Exam.xml" relativeToChangelogFile="false"/>
<!-- JHipster will add liquibase changelogs here -->

```