Java Virtual Machine
---

List questions:

1. [What is a Java Virtual Machine (JVM)?](#1-what-is-a-java-virtual-machine-jvm-)
1. [Memory Management with JVM?](#2-memory-management-with-jvm-)
1. [Explain the Difference amongst JVM Specification, JVM Implementation, JVM Runtime?](#3-explain-the-difference-amongst-jvm-specification-jvm-implementation-jvm-runtime-)
1. [Why is the source file named after the class?](#4-why-is-the-source-file-named-after-the-class-)
1. [Which class should be compiled first?](#5-which-class-should-be-compiled-first-)
1. [What are the steps in compiling a class?](#6-what-are-the-steps-in-compiling-a-class-)

---

#####1. What is a Java Virtual Machine (JVM)? [&#10548;](#java-virtual-machine)

Java virtual machine is a runtime environment required for execution of a Java application.

Every Java application runs inside a runtime instance of some concrete implementation of abstract specifications of JVM.

JVM is crux of "platform independent" nature of the language.

***JVM translates bytecode into machine language***

Every Java program is first compiled into an intermediate language called Java bytecode. The JVM is used primarily for 2 things:

* The first is to translate the bytecode into the machine language for a particular computer, and the second thing is to actually execute the corresponding machine-language instructions as well.
* The JVM and bytecode combined give Java its status as a "portable" language – this is because Java bytecode can be transferred from one machine to another.

***Machine language is OS dependent***

***The JVM is not platform independent***

***Reference:*** [programmerinterview](http://www.programmerinterview.com/index.php/java-questions/jvm-platform-dependent/) , [interviewjava](http://www.interviewjava.com/2007/04/what-is-java-virtual-machine-jvm.html), [roseindia](http://www.roseindia.net/java/java-virtual-machine.shtml) , [artima](http://www.artima.com/insidejvm/ed2/jvm.html)

#####2. Memory Management with JVM? [&#10548;](#java-virtual-machine)

The Java language in combination with runtime eliminates the problems of memory management and corrupted pointers.

1. There is no explicit allocation of memory in Java, memory is allocated only to objects.
2. JVM's heap stores all objects created.
3. JVM ask the operating system for enough memory to run the JVM itself and some free memory for the  application to create new objects.
4. If the free memory area is getting too small, the JVM will ask the operating system for more and if there is no more additional memory available from the operating system, then JVM stops the application and issues the "Out of memory error".
5. The Java runtime employs a garbage collector to reclaim the memory occupied by an object.

#####3. Explain the Difference amongst JVM Specification, JVM Implementation, JVM Runtime? [&#10548;](#java-virtual-machine)

JVM Specification = Java programming language + Java Virtual Machine architecture +  Java class-file format.

#####4. Why is the source file named after the class? [&#10548;](#java-virtual-machine)

The Java source file naming convention is not a standard specified by the Java language but is a common feature of Java compilers, such as javac, to help locate source code. The source content of a Java class is known as a compilation unit. By storing the compilation unit in a file that is named after the class, the compiler can locate any supporting classes by name and compile those too.

This convention also extends to package names. Most Java compilers expect source code to be stored in directories whose names match their package hierarchy. Thus the source code for a class named Example in the package com.domain.util might be stored in a file with the path c:\src\com\domain\util\Example.java

***Reference:*** [codeproject](http://www.codeproject.com/Articles/708722/Myths-about-FileName-Should-be-Same-as-Class-Name) , [javabeat](http://javabeat.net/jvmjrejava-compiler-interview-questions/2/)

#####5. Which class should be compiled first? [&#10548;](#java-virtual-machine)

Sometimes you will find that trial and error will give you the answer you need. If you are using the Sun compiler, javac, the compiler will compile any other classes that your target class depends on, provided the other source files are in the same directory hierarchy as the first and the sub-directory names reflect the package hierarchy of the classes.

#####6. What are the steps in compiling a class? [&#10548;](#java-virtual-machine)
