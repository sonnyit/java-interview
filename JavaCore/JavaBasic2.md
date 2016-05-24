Java Basics 2
---------------

List questions:

1. [What is the right data type to represent a price in Java?](#what-is-the-right-data-type-to-represent-a-price-in-java-)
1. [How do you convert bytes to String?](#how-do-you-convert-bytes-to-string-)
1. [Can we cast an int value into byte variable? what will happen if the value of int is larger than byte?](#can-we-cast-an-int-value-into-byte-variable-what-will-happen-if-the-value-of-int-is-larger-than-byte-)
1. [There are two classes B extends A and C extends B, Can we cast B into C e.g. C = (C) B;](#there-are-two-classes-b-extends-a-and-c-extends-b-can-we-cast-b-into-c-eg-c--c-b-)
1. [Is ++ operator is thread-safe in Java?](#is--operator-is-thread-safe-in-java-)
1. [Difference between a = a + b and a += b ?](#difference-between-a--a--b-and-a--b--)
1. [Can I store a double value in a long variable without casting?](#can-i-store-a-double-value-in-a-long-variable-without-casting-)
1. [What will this return 3*0.1 == 0.3? true or false?](#what-will-this-return-301--03-true-or-false-)
1. [Which one will take more memory, an int or Integer?](#which-one-will-take-more-memory-an-int-or-integer-)
1. [Why is String Immutable in Java?](#why-is-string-immutable-in-java-)
1. [Can we use String in the switch case?](#can-we-use-string-in-the-switch-case-)
1. [What is a compile time constant in Java? What is the risk of using it?](#what-is-a-compile-time-constant-in-java-what-is-the-risk-of-using-it-)
1. [The difference between DOM and SAX parser in Java?](#the-difference-between-dom-and-sax-parser-in-java-)
1. [Tell me 3 features introduced on JDK 1.7?]()
1. [Tell me 5 features introduced in JDK 1.8?]()

---

1. ##### What is the right data type to represent a price in Java? [&#10548;](#java-basics-2)

  BigDecimal if memory is not a concern and Performance is not critical, otherwise double with predefined precision.

1. ##### How do you convert bytes to String? [&#10548;](#java-basics-2)

  You can convert bytes to the string using string constructor which accepts byte[], just make sure that right character encoding otherwise platform's default character encoding will be used which may or may not be same.

1. ##### Can we cast an int value into byte variable? what will happen if the value of int is larger than byte? [&#10548;](#java-basics-2)

  Yes, we can cast but int is 32 bit long in java while byte is 8 bit long in java so when you cast an int to byte higher 24 bits are lost and a byte can only hold a value from -128 to 128.

1. ##### There are two classes B extends A and C extends B, Can we cast B into C e.g. C = (C) B; [&#10548;](#java-basics-2)

  [answer](http://javarevisited.blogspot.sg/2012/12/what-is-type-casting-in-java-class-interface-example.html)

1. ##### Is ++ operator is thread-safe in Java? [&#10548;](#java-basics-2)

  No it's not a thread safe operator because its involve multiple instructions like reading a value, incriminating it and storing it back into memory which can be overlapped between multiple threads.

1. ##### Difference between a = a + b and a += b ? [&#10548;](#java-basics-2)

  The += operator implicitly cast the result of addition into the type of variable used to hold the result. When you add two integral variable e.g. variable of type byte, short, or int then they are first promoted to int and them addition happens. If result of addition is more than maximum value of a then a + b will give compile time error but a += b will be ok as shown below:

  ```
  byte a = 127;
  byte b = 127;
  b = a + b; // error : cannot convert from int to byte
  b += a; // ok
  ```

1. ##### Can I store a double value in a long variable without casting? [&#10548;](#java-basics-2)

  No, you cannot store a double value into a long variable without casting because the range of double is more  that long and you we need to type cast. It's not difficult to answer this question but many developer get it wrong due to confusion on which one is bigger between double and long in Java.

  [detail](http://java67.blogspot.com/2014/11/how-to-convert-double-to-long-in-java-example.html)

1. ##### What will this return 3*0.1 == 0.3? true or false? [&#10548;](#java-basics-2)

  This is one of the really tricky questions. Out of 100, only 5 developers answered this question and only of them have explained the concept correctly. The short answer is false because some floating point numbers can not be represented exactly.

1. ##### Which one will take more memory, an int or Integer? [&#10548;](#java-basics-2)

  An Integer object will take more memory an Integer is the an object and it  store meta data overhead about the object and int is primitive type so its takes less space.

1. ##### Why is String Immutable in Java? [&#10548;](#java-basics-2)

  One of my favorite Java interview question. The String is Immutable in java because java designer thought that string will be heavily used and making it immutable allow some optimization easy sharing same String object between multiple clients. See the link for the more detailed answer. This is a great question for Java programmers with less experience as it gives them food for thought, to think about how things works in Java, what Java designers might have thought when they created String class etc.

  [detail](http://java67.blogspot.sg/2014/01/why-string-class-has-made-immutable-or-final-java.html)

1. ##### Can we use String in the switch case? [&#10548;](#java-basics-2)

  Yes from Java 7 onward we can use String in switch case but it is just syntactic sugar. Internally string hash code is used for the switch. See the detailed answer for more explanation and discussion.

  [detail](http://javarevisited.blogspot.sg/2011/08/string-switch-case-jdk7-example.html)

1. ##### What is a compile time constant in Java? What is the risk of using it? [&#10548;](#java-basics-2)

  public static final variables are also known as a compile time constant, the public is optional there. They are replaced with actual values at compile time because compiler know their value up-front and also knows that it cannot be changed during run-time. One of the problem with this is that if you happened to use a public static final variable from some in-house or third party library and their value changed later than your client will still be using old value even after you deploy a new version of JARs. To avoid that, make sure you compile your program when you upgrade dependency JAR files.

1. ##### The difference between DOM and SAX parser in Java? [&#10548;](#java-basics-2)

  Another common Java question but from XML parsing topic. It's rather simple to answer and that's why many interviewers prefers to ask this question on the telephonic round.

  DOM parser loads the whole XML into memory to create a tree based DOM model which helps it quickly locate nodes and make a change in the structure of XML.

  While SAX parser is an event based parser and doesn't load the whole XML into memory. Due to this reason DOM is faster than SAX but require more memory and not suitable to parse large XML files.

  [detail](http://javarevisited.blogspot.sg/2011/12/difference-between-dom-and-sax-parsers.html)

1. ##### Tell me 3 features introduced on JDK 1.7? [&#10548;](#java-basics-2)

  This is one of the good questions I ask to check whether the candidate is aware of recent development in Java technology space or not. Even though JDK 7 was not a big bang release like JDK 5 or JDK 8, it still has a lot of good feature to count on e.g.

  * try-with-resource statements, which free you from closing streams and resources when you are done with that, Java automatically closes that.
  * Fork-Join pool to implement something like the Map-reduce pattern in Java.
  * Allowing String variable and literal into switch statements.
  * Diamond operator for improved type inference, no need to declare generic type on the right-hand side of variable declaration anymore, results in more readable and succinct code.
  * Another worth noting feature introduced was improved exception handling e.g. allowing you to catch multiple exceptions in the same catch block.

  [detail](http://javarevisited.blogspot.sg/2014/04/10-jdk-7-features-to-revisit-before-you.html)

1. ##### Tell me 5 features introduced in JDK 1.8?

  This is the follow-up question of the previous one. Java 8 is path breaking release in Java's history, here are the top 5 features from JDK 8 release

  * Lambda expression, which allows you pass an anonymous function as object.
  * Stream API, take advantage of multiple cores of modern CPU and allows you to write succinct code.
  * Date and Time API, finally you have a solid and easy to use date and time library right into JDK.
  * Extension methods, now you can have static and default method into your interface.
  * Repeated annotation, allows you apply the same annotation multiple times on a type.

  [detail](http://javarevisited.blogspot.sg/2014/02/10-example-of-lambda-expressions-in-java8.html)
