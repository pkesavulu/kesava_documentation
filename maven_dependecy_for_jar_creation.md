# To add this dependency in pox.ml in side of "plugin"
---
```
		<plugin>	
			<artifactId>maven-assembly-plugin</artifactId>
			<configuration>
				<descriptorRefs>
					<descriptorRefs>jar-with-dependencies</descriptorRefs>
				</descriptorRefs>
				<archive>
					<manifest>
						<mainClass>com.pack.class_name</mainClass>
					</manifest>
				</archive>
				<compilerArgs>
					<arg>${jvm.options}</arg>
				</compilerArgs>	
			</configuration>
			<executions>
				<execution>
					<id>make-assembly</id>
					<phase>package</phase>
					<goals>
						<goal>single</goal>
					</goals>
				</execution>
			</executions>
		</plugin>	
   
```   
> After you should run below command from project location.
 
 mvn clean install
 
 > Finally jar exported in target location.
 
 project_name-jar-with-dependencies.jar
 
 > To run the below jar like this 
 
 java -jar project_name-jar-with-dependencies.jar com.pack.class_name <arguments>
 
 # alter native jar file creation
 ---
 

> You could combine the maven-shade-plugin and maven-jar-plugin.

> The maven-shade-plugin packs your classes and all dependencies in a single jar file.

> Configure the maven-jar-plugin to specify the main class of your executable jar (see Set Up The Classpath, chapter "Make The Jar Executable").

> Example POM configuration for maven-jar-plugin:


 ```
 	<plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-jar-plugin</artifactId>
            <version>2.3.2</version>
            <configuration>
                <archive>
                    <manifest>
                        <addClasspath>true</addClasspath>
                        <mainClass>sos.app.ExcelJsonApp</mainClass>       <!-- fully quailified class name -->
                    </manifest>
                </archive>
            </configuration>
        </plugin>
			 
```

> Finally create the executable jar by invoking:

> mvn clean package shade:shade

> if you need more information try to click this link https://stackoverflow.com/questions/574594/how-can-i-create-an-executable-jar-with-dependencies-using-maven
