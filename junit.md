Junit:-
---

junit use to test the project automatically using some testcases.



plug with ANT:- provided by apache.
---
A -> Another
N -> Neat
T -> Tool

- use this tool to build the xml file. 
- use this xml file to execute the program.
- junit use this ant. 

set the enviorment:-
---
1.download apache ant
2.set Ant enviorment
3.download Junit Archive
4.create folder structure for ANT
5.main package including src,test,lib,build.xml

integrate eclipse:-
---
1.download junit and download eclipse.
2.set envirment file(in eclipse right click on project->click build path->click configuration build path->click library->click add external jars(Junit-4.10.jars)->click apply)

Annotations:-
---
- use this annotation to decided the wich method execute first and next.
 @BeforecClass -> only once executed for example single dirver to execute all the test class then we go for this annotation.
 @Beforec -> different dirver for different test cases simple we go for this driver. (i want to execute one method every time before my test case then we go for this.)
 @Test -> this annotation use to test the method
 @After -> if u want to execute methods after test case we use this 
 @AfterClass -> same as like above but only once
 @Ignore -> if don't want to execute a method simple we use this.

componets of junit Framework:-
---

1.Fixtures
2.Test suites
3.Test runners
4.Junit classes


classes:-
---

1.assert class 
  1.1.assertEquals ->check it equal or not
  1.2.assertFales -> check it given one false or not
  1.3.assertNotNull -> check it given object not null or not
  1.4.assertNull -> check it given object null
  1.5.assertTrue -> check give condition is true or not
  
2. TestCase class -> use to check ur test cases like if you want any information about our test case then we use this testcases.
  2.1.int countTestCases()-> count how many test cases are executed
  2.2.TestResult createResult()-> 
  2.3.String getName()-> we want runing some test case at the time i want know what test case we are running.
  2.4.TestResult run()-> if we want to run more than one test case explicitly then we go for this.
  2.5.void run(TestResult result) -> 
  2.6.void setName(String name) -> if u want to set new name for test case then we use this test case
  2.7.void setup() -> use to insitilize the values
  2.8.void tearDown() -> use to close or destroy the insitilization values.
  2.9.String toString() -> use this method to print the content of the object.

3.TestResult class
	3.1.void addError(Test test,Throwable t)
	3.2.void addFailure(Test test,AssertionFailedError t)
	3.3.void endTest(Test test)
	3.4.int errorCount()
	3.5.Enumeration<TestFailure> errors()
	3.6.int failureCount()
	3.7.void run(TestCase test)
	3.8.int runCount()
	3.9.void startTest(Test test)
	3.10.void stop()
  
  
 Timeout annotation:-
 ---
 @Test(timeout = 500) -> here 500 is milliseconds like 500 milliseconds

 Ignore annotation:-
 ---
 @Ignore -> we use this annotation to ignore perticular test case.

 
 