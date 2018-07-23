# eclipse installation:
---

1. Download eclipse [here](https://wiki.eclipse.org/Eclipse.ini)

2. To add M2Eclipse plugin 

   2.1 Open eclipse and click add button.
   2.2 Give Name as "M2Eclipse" and Location "http://download.eclipse.org/technology/m2e/releases" and click the ok button.
   2.3 Next step click "selectAll" button and click the "Next" button in bottom.
   2.4 Finally click the "finish" button.

  > Note : If you face any problem at M2Eclipse installation time to follow below step in your project directory. 

      1. Go to you project directory "C:\git\sos\Thales" and remove the .setting folder
      2. Go to "C:\git\sos\Thales\excel_mining" and remove the .project,.classpath and .setting folder and close eclipse.
      3. Go to project directory (C:\git\sos\Thales) and run this command "mvn clean compile eclipse:eclipse" using gitBash.
      4. Finally open the Eclipse.

3. To follow the below steps to create project build path.

   3.1 Go to eclipse - > windows -> java -> Installed JREs -> Add -> Standard VM -> Next -> Directory (choose jdk path :C:\apps\java-1.8_171) - > Finish -> Apply and close.
   3.2 To restart eclipse. 	

4. If your facing any issue like this to follow 3 step. 

```
  Syntax error, parameterized types are only available if source level is 1.5 or greater
```

	  