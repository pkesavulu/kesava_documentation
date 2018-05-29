# Maven document


* maven is use to download dependencies automatically. Here we have pom.xml file we just add the dependecy code it take all the dependencies automatically for your projects.

* Without maven it is very defficulte to download all the dependencies for project.

* In your project spring related jars,hibernate related jars, mysql related jars,etc .. when we download manually it is very difficult. 
 So we use maven to download those all very easly just we drag the xml code for spring,hibernet,mysql,etc.. it taken very thing automatically.

* here we have 2 repositories like one is remote and second is local 

* first time only it using remote repository for downloading jar what were you mentioned in pom.xml file push into local repository . After project using only local repository. 


> To click below link for maven video.

- [maven](https://www.youtube.com/watch?v=uEYjXpMDJiU) 

## Pom.xml

``` maven pom.xml

    <groupId>com.project</groupId>
    <artifactId>project name</artifactId>
    <version>5.0.4.RELEASE</version>
    <packaging>jar<packaging>
    
```

> group ID : com.project --> it is like package name

> Artifactore ID : projectname - > it is like project name

> package name : com.project.projectname --> it is combination of group Id and Artifactore Id

> version : 5.0.1 --> version no.

> packaging : jar , war ,etc --> finally we create all the class fiels as jar(core java project) or war(web application projects)

## spring dependencies add in pom.xml file

``` spring dependency

<!-- https://mvnrepository.com/artifact/org.springframework/spring-core -->

<dependencies>
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-core</artifactId>
    <version>5.0.4.RELEASE</version>
</dependency>
</dependencies>

```

* pom.xml file contains dependencies tag. 

* dependencies tag contain no.of dependency tags.

* each dependency tag contain groupID,artifactId and version tags.


