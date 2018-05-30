1.lambda expression
2.functional interfaces
3.defualt methos in interfaces(concreate methods)
4.static methods in interfaces
5.predicate----
6.function ----   predefined functional interfaces.
7.consumer ----
8.method reference & constructore reference by double colon(::) operator.
9.streams API ()
10.Date and Time API (joda API)



use of 1.8 java:
---------------

1. To simplify programming
2. To utilise functional programing benefits in java
3. To enable paralle programing

lambda expression:-
------------------

lisp -> it is programing languages use the lambda expressions	 


why lambdas:

1. Enables functional programming
2. readable  and concise code
3. Easier-to-use APIs and libraries
4. Enables support for parallel processing


ex:-
 
1. In before lambda expressions(1.7v):

public void perform(){

system.out.println("hello world");

}

2. In lambda expression(1.8 v) to assign method as variable

aBlockofCode= () -> system.out.println("hello world");


example 2:

1. public int doubleNumber(int a){

    return a*2;
  }

using 1.8 lambda expression:-


1. doubleNumber = (int a) -> return a*2;



example3:

1.divided = (int a,int b) ->{

	if(b==0) return 0;
	return a/b;

}

example4:

1. stringLengthcount = (string s) -> s.lenght();


