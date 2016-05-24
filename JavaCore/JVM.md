Java Virtual Machine
---

List questions:

1. [What is a Java Virtual Machine (JVM)?](#what-is-a-java-virtual-machine-jvm-)
1. [Memory Management with JVM?](#memory-management-with-jvm-)
1. [Explain the Difference amongst JVM Specification, JVM Implementation, JVM Runtime?](#explain-the-difference-amongst-jvm-specification-jvm-implementation-jvm-runtime-)
1. [What is the size of int in 64-bit JVM?](#what-is-the-size-of-int-in-64-bit-jvm-)
1. [Why is the source file named after the class?](#why-is-the-source-file-named-after-the-class-)
1. [Which class should be compiled first?](#which-class-should-be-compiled-first-)
1. [What are the steps in compiling a class?](#what-are-the-steps-in-compiling-a-class-)
1. [The difference between Serial and Parallel Garbage Collector?](#the-difference-between-serial-and-parallel-garbage-collector-)
1. [A difference between WeakReference and SoftReference in Java?](#a-difference-between-weakreference-and-softreference-in-java-)
1. [How do WeakHashMap works?](#how-do-weakhashmap-works-)
1. [What is -XX:+UseCompressedOops JVM option? Why use it?](#what-is--xxusecompressedoops-jvm-option-why-use-it-)
1. [How do you find if JVM is 32-bit or 64-bit from Java Program?](#how-do-you-find-if-jvm-is-32-bit-or-64-bit-from-java-program-)
1. [What is the maximum heap size of 32-bit and 64-bit JVM?](#what-is-the-maximum-heap-size-of-32-bit-and-64-bit-jvm-)
1. [What is the difference between JRE, JDK, JVM and JIT?](#what-is-the-difference-between-jre-jdk-jvm-and-jit-)
1. [Explain Java Heap space and Garbage collection?](#explain-java-heap-space-and-garbage-collection-)
1. [How do you find memory usage from Java program? How much percent of the heap is used](#how-do-you-find-memory-usage-from-java-program-how-much-percent-of-the-heap-is-used-)
1. [What is the difference between stack and heap in Java?](#what-is-the-difference-between-stack-and-heap-in-java-)

---

1. ##### What is a Java Virtual Machine (JVM)? [&#10548;](#java-virtual-machine)

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

2. ##### Memory Management with JVM? [&#10548;](#java-virtual-machine)

  The Java language in combination with runtime eliminates the problems of memory management and corrupted pointers.

  1. There is no explicit allocation of memory in Java, memory is allocated only to objects.
  2. JVM's heap stores all objects created.
  3. JVM ask the operating system for enough memory to run the JVM itself and some free memory for the  application to create new objects.
  4. If the free memory area is getting too small, the JVM will ask the operating system for more and if there is no more additional memory available from the operating system, then JVM stops the application and issues the "Out of memory error".
  5. The Java runtime employs a garbage collector to reclaim the memory occupied by an object.

1. ##### Explain the Difference amongst JVM Specification, JVM Implementation, JVM Runtime? [&#10548;](#java-virtual-machine)

  JVM Specification = Java programming language + Java Virtual Machine architecture +  Java class-file format.

1. ##### What is the size of int in 64-bit JVM? [&#10548;](#java-virtual-machine)

  The size of an int variable is constant in Java, it's always 32-bit irrespective of platform. Which means the size of primitive int is same in both 32-bit and 64-bit Java virtual machine.

  It's always 32 bits or 4 bytes.

1. ##### Why is the source file named after the class? [&#10548;](#java-virtual-machine)

  The Java source file naming convention is not a standard specified by the Java language but is a common feature of Java compilers, such as javac, to help locate source code. The source content of a Java class is known as a compilation unit. By storing the compilation unit in a file that is named after the class, the compiler can locate any supporting classes by name and compile those too.

  This convention also extends to package names. Most Java compilers expect source code to be stored in directories whose names match their package hierarchy. Thus the source code for a class named Example in the package com.domain.util might be stored in a file with the path c:\src\com\domain\util\Example.java

  ***Reference:*** [codeproject](http://www.codeproject.com/Articles/708722/Myths-about-FileName-Should-be-Same-as-Class-Name) , [javabeat](http://javabeat.net/jvmjrejava-compiler-interview-questions/2/)

1. ##### Which class should be compiled first? [&#10548;](#java-virtual-machine)

  Sometimes you will find that trial and error will give you the answer you need. If you are using the Sun compiler, javac, the compiler will compile any other classes that your target class depends on, provided the other source files are in the same directory hierarchy as the first and the sub-directory names reflect the package hierarchy of the classes.

1. ##### What are the steps in compiling a class? [&#10548;](#java-virtual-machine)

1. ##### The difference between Serial and Parallel Garbage Collector? [&#10548;](#java-virtual-machine)

  Even though both the serial and parallel collectors cause a stop-the-world pause during Garbage collection. The main difference between them is that a serial collector is a default copying collector which uses only one GC thread for garbage collection while a parallel collector uses multiple GC threads for garbage collection.

  [detail](http://javarevisited.blogspot.sg/2011/04/garbage-collection-in-java.html)

1. ##### A difference between WeakReference and SoftReference in Java? [&#10548;](#java-virtual-machine)

  Though both WeakReference and SoftReference helps garbage collector and memory efficient, WeakReference becomes eligible for garbage collection as soon as last strong reference is lost but SoftReference even thought it can not prevent GC, it can delay it until JVM absolutely need memory.

  [detail](http://javarevisited.blogspot.sg/2014/03/difference-between-weakreference-vs-softreference-phantom-strong-reference-java.html)

1. ##### How do WeakHashMap works? [&#10548;](#java-virtual-machine)

  WeakHashMap works like a normal HashMap but uses WeakReference for keys, which means if the key object doesn't have any reference then both key/value mapping will become eligible for garbage collection.

1. ##### What is -XX:+UseCompressedOops JVM option? Why use it? [&#10548;](#java-virtual-machine)

  When you go migrate your Java application from 32-bit to 64-bit JVM, the heap requirement suddenly increases, almost double, due to increasing size of ordinary object pointer from 32 bit to 64 bit. This also adversely affect how much data you can keep in CPU cache, which is much smaller than memory. Since main motivation for moving to 64-bit JVM is to specify large heap size, you can save some memory by using compressed OOP. By using -XX:+UseCompressedOops, JVM uses 32-bit OOP instead of 64-bit OOP.

  [detail](http://javarevisited.blogspot.com/2012/06/what-is-xxusecompressedoops-in-64-bit.html)

1. ##### How do you find if JVM is 32-bit or 64-bit from Java Program? [&#10548;](#java-virtual-machine)

  You can find that by checking some system properties like sun.arch.data.model or os.arch

  [detail](http://javarevisited.blogspot.sg/2012/01/find-jvm-is-32-or-64-bit-java-program.html)

1. ##### What is the maximum heap size of 32-bit and 64-bit JVM? [&#10548;](#java-virtual-machine)

  Theoretically, the maximum heap memory you can assign to a 32-bit JVM is 2^32 which is 4GB but practically the limit is much smaller. It also varies between operating systems e.g. form 1.5GB in Windows to almost 3GB in Solaris. 64-bit JVM allows you to specify larger heap size, theoretically 2^64 which is quite large but practically you can specify heap space up to 100GBs. There are even JVM e.g. Azul where heap space of 1000 gigs is also possible.

  [detail](http://javarevisited.blogspot.sg/2013/04/what-is-maximum-heap-size-for-32-bit-64-JVM-Java-memory.html)

1. ##### What is the difference between JRE, JDK, JVM and JIT? [&#10548;](#java-virtual-machine)

  * **JRE** stands for Java run-time and it's required to run Java application.
  * **JDK** stands for Java development kit and provides tools to develop Java program e.g. Java compiler. It also contains JRE.
  * The **JVM** stands for Java virtual machine and it's the process responsible for running Java application.
  * The **JIT** stands for Just In Time compilation and helps to boost the performance of Java application by converting Java byte code into native code when the crossed certain threshold i.e. mainly hot code is converted into native code.

  [detail](http://javarevisited.blogspot.sg/2011/12/jre-jvm-jdk-jit-in-java-programming.html)

1. ##### Explain Java Heap space and Garbage collection? [&#10548;](#java-virtual-machine)

  When a Java process is started using java command, memory is allocated to it. Part of this memory is used to create heap space, which is used to allocate memory to objects whenever they are created in the program. Garbage collection is the process inside JVM which reclaims memory from dead objects for future allocation.

  ![Java Heap](https://3.bp.blogspot.com/-DqV12_uIeZ4/VhDqtPCVIVI/AAAAAAAAD48/uqWZB0BgZUI/s400/java_heaps_memory.jpg)

  [detail](http://javarevisited.blogspot.sg/2011/05/java-heap-space-memory-size-jvm.html)

1. ##### How do you find memory usage from Java program? How much percent of the heap is used [&#10548;](#java-virtual-machine)

  You can use memory related methods from java.lang.Runtime class to get the free memory, total memory and maximum heap memory in Java.

  By using these methods, you can find out how many percents of the heap is used and how much heap space is remaining.
  * Runtime.freeMemory() return amount of free memory in bytes
  * Runtime.totalMemory() returns total memory in bytes
  * Runtime.maxMemory() returns maximum memory in bytes.

1. ##### What is the difference between stack and heap in Java? [&#10548;](#java-virtual-machine)

  Stack and heap are different memory areas in the JVM and they are used for different purposes.

  * The stack is used to hold method frames and local variables .
  * While objects are always allocated memory from the heap.
  * The stack is usually much smaller than heap memory and also didn't shared between multiple threads, but heap is shared among all threads in JVM.

  ![Java-heap-stack](http://1.bp.blogspot.com/-NZeVo83YJAA/VhDrDO0oWtI/AAAAAAAAD5E/mEek8Ll7NfU/s1600/Difference%2Bbetween%2Bstack%2Band%2Bheap%2Bmemory%2Bin%2BJava.gif)

  [detail](http://javarevisited.blogspot.com/2013/01/difference-between-stack-and-heap-java.html)

1. ##### [&#10548;](#java-virtual-machine)

1. ##### [&#10548;](#java-virtual-machine)
