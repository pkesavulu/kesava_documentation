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
 
 
