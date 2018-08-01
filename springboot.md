spring boot
---

create sprin boot application using
1.eclipse maven
2.start.sping.io
3.eclipse sts


run spirn boot application using
1.java CLI
2.eclipse IDE

 dependencies added in pom.xml:-
 ---
 <properties>
 <java.version>1.8</java.version>
 </properties>
 
 <parent>
 <groupId>org.springframwork.boot</groupId>
 <artifcatId>spring-boot-starter-parent</artifcatId>
 <version>1.5.4.RELEASE</version>
 </parent>
 
 <dependencies>
 <dependency>
 <groupId>org.springframwork.boot</groupId>
 <artifcatId>spring-boot-starter-web</artifcatId> ----> it download all the dependencies for our application
 </dependency>
 </dependencies>	
 
 
 simple program:-
 ---
 
 main class:-
 ---
 @SpringBootApplication
 public class Helloworldspringbootapp{
 
 public static void main(String[] args){
 
 SpringApplication.run(Helloworldspringbootapp.class,args)
 }
 }
 
 rest controller:-
---

@RestController
public class Helloworldcontroller{

@RequestMapping(value="/")
public string hello(){

system.out.println("helloworld")

}
}

