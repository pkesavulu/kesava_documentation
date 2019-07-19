Jenkins:-
---
To Run jenkins in jdk 10 version use below command:-
---
C:\apps\jdk_10_02\bin\java --add-modules java.xml.bind -jar jenkins.war --enable-future-java --httpPort=8080 --prefix=/jenkins


how to install jenkins:-
---
1.download jenkins from https://updates.jenkins-ci.org/download/war/
2.create folder in this location C:\apps\jenkins
3.past jenkins.war file here
4.run below command for jekins

	java -jar jenkins.war(if it's jdk8)
	 (or)
	C:\apps\jdk_10_02\bin\java --add-modules java.xml.bind -jar jenkins.war --enable-future-java --httpPort=8080 --prefix=/jenkins(if it's jdk10)
5.open jenkins in localhost:8080 (or) localhost:8080/jenkins
6.install suggested plugins
7.finally open dashboard.

how to integrate with tomcat:-
---

1.tomcat 5 or above
2.java 7 or above require
3.download tomcat (tomcat 8)
4.uzip and place any place on ure system
5.copy/place the jenkins.war file inside webapps folder in tomcat
6. goto command promt
  6.1.goto tomcat/bin direcotry
  6.2.make all files executable:chmod +x *.sh
7.start tomcat:/bin/startup.sh
8.verify if tomcat started or not.(localhost:8080)
9.verify if jenkins running on tomcat http://localhost:8080/jenkins
Note:-
1.To start jenkins(standalone) on a different port
2.use port number like this java -jar jenkins.war--httpPort=9090

jenkins 3 - How to change Home Directory
---
1.check your current direcotry
2.create a new direcotry(which will be new home dir)
3.copy all data from old direcotry to new direcotry
4.change env variable - JENKINS_HOME and set to new direcotry
 4.1.Windows-change environment variable(same like java path setting in windows) 
5.restart jenkins(in browser:localhost:8080/restart)
6.To view all the system info(localhost:8080/systeminfo)
jenkins 4 - how to use CLI -command line interface
---

i.easier
ii.faster
iii.memory management(efficient)
iv.continous integration

1.start command line(java -jar jekins.war --httpPort=9090)
2.goto manage jenkins -> configure Global Security
3.goto -> http://localhost:8080/cli/
4.download jenkins-cli jar palce at any location
5.Test the jekins command line is working
java -jar jenkins-cli.jar -s http://localhost:8080/help


jenkins 5: How to create and manage users
---
1.create new users
2.Configure users
3.create and manage user roles
	(Role Strategy Plugin -download-restar jenkins)
4.Manage Jenkins-> configure Global Security ->Authoristation->Role Base Strategy

jenkins 6: Basic Configurations
---
1.Manage jekins

	