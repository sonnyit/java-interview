Java Concurrency
---

List questions:

1. [What is Thread in Java?](#what-is-thread-in-java-)
1. [Describe synchronization in respect to multi-threading. What is synchronization?](#describe-synchronization-in-respect-to-multi-threading-what-is-synchronization-)
1. [Explain different ways of using thread?](#explain-different-ways-of-using-thread-)
1. [How to stop a thread in Java?](#how-to-stop-a-thread-in-java-)
1. [What happens when an Exception occurs in a thread?](#what-happens-when-an-exception-occurs-in-a-thread-)
1. [How do you share data between two thread in Java?](#how-do-you-share-data-between-two-thread-in-java-)
1. [What is the difference between preemptive scheduling and time slicing?](#what-is-the-difference-between-preemptive-scheduling-and-time-slicing-)
1. [When a thread is created and started, what is its initial state?](#when-a-thread-is-created-and-started-what-is-its-initial-state-)
1. [What is a thread local variable in Java?](#what-is-a-thread-local-variable-in-java-)
1. [When to use Runnable vs Thread in Java?](#When-to-use-runnable-vs-thread-in-java-)
1. [Thread vs Runnable, run() vs start()](#thread-vs-runnable-run-vs-start-)
1. [Describe different ways to create a thread.](#describe-different-ways-to-create-a-thread-)
1. [Synchronization of Java blocks and methods](#synchronization-of-java-blocks-and-methods-)
1. [Explain usage of the couple wait()/notify()](#explain-usage-of-the-couple-waitnotify-)
1. [Why wait and notify method are called from synchronized block?](#why-wait-and-notify-method-are-called-from-synchronized-block-)
1. [What is the difference between notify and notifyAll in Java?](#what-is-the-difference-between-notify-and-notifyall-in-java-)
1. [Why wait, notify and notifyAll are not inside thread class?](#why-wait-notify-and-notifyall-are-not-inside-thread-class-)
1. [How do you call wait() method? using if block or loop? Why?](#how-do-you-call-wait-method-using-if-block-or-loop-why-)
1. [What are differences between wait and sleep method in Java?](#what-are-differences-between-wait-and-sleep-method-in-java-)
1. [What does Volatile keyword mean?](#what-does-volatile-keyword-mean-)
1. [Difference between synchronized and volatile keyword in Java](#difference-between-synchronized-and-volatile-keyword-in-java-)
1. [The difference between Serializable and Externalizable in Java?](#the-difference-between-serializable-and-externalizable-in-java-)
1. [java.util.concurrent.* , what utils do you know?](#javautilconcurrent--what-utils-do-you-know-)
1. [ThreadLocal, what for are they needed? Does child thread see the value of parent ThreadLocal?](#threadlocal-what-for-are-they-needed-does-child-thread-see-the-value-of-parent-threadlocal-)
1. [Recommendations to avoid deadlocks.](#recommendations-to-avoid-deadlocks-)
1. [What is daemon thread and which method is used to create the daemon thread?](#what-is-daemon-thread-and-which-method-is-used-to-create-the-daemon-thread-)
1. [What method must be implemented by all threads?](#what-method-must-be-implemented-by-all-threads-)
1. [What is the difference between process and thread?](#what-is-the-difference-between-process-and-thread-)
1. [What is an immutable object? How do you create an Immutable object in Java?](#what-is-an-immutable-object-how-do-you-create-an-immutable-object-in-java-)
1. [Can we create an Immutable object, which contains a mutable object?](#can-we-create-an-immutable-object-which-contains-a-mutable-object-)
1. [What are the states associated in the thread?](#what-are-the-states-associated-in-the-thread-)
1. [When you will synchronize a piece of your code?](#when-you-will-synchronize-a-piece-of-your-code-)
1. [What is deadlock? Example of deadlock.](#what-is-deadlock-example-of-deadlock-)
1. [Are there any global variables in Java, which can be accessed by other part of your program?](#are-there-any-global-variables-in-java-which-can-be-accessed-by-other-part-of-your-program-)
1. [What are Callable and FutureTask interfaces?](#what-are-callable-and-futuretask-interfaces-)
1. [What is the difference between the interrupted() and isInterrupted() method in Java?](#what-is-the-difference-between-the-interrupted-and-isinterrupted-method-in-java)
1. [What is the difference between Runnable and Callable in Java?](#what-is-the-difference-between-runnable-and-callable-in-java-)
1. [What is the difference between CyclicBarrier and CountDownLatch in Java?](#what-is-the-difference-between-cyclicbarrier-and-countdownlatch-in-java-)
1. [What is thread-safety? Is Vector a thread-safe class?](#what-is-thread-safety-is-vector-a-thread-safe-class-)
1. [What is race condition in Java? Given one example?](#what-is-race-condition-in-java-given-one-example-)
1. [What is Java Memory model?](#what-is-java-memory-model-)
1. [What is Executors framework?](#what-is-executors-framework-)
1. [What is AtomicInteger](#what-is-atomicinteger-)
1. [Why should you check condition for waiting in a loop?](#why-should-you-check-condition-for-waiting-in-a-loop-)
1. [What is the difference between synchronized and concurrent collection in Java?](#what-is-the-difference-between-synchronized-and-concurrent-collection-in-java-)
1. [What is the difference between Stack and Heap in Java?](#what-is-the-difference-between-stack-and-heap-in-java-)
1. [What is thread pool? Why should you thread pool in Java?](#what-is-thread-pool-why-should-you-thread-pool-in-java-)
1. [Write code to solve Producer Consumer problem in Java?](#write-code-to-solve-producer-consumer-problem-in-java-)
1. [How do you avoid deadlock in Java? Write Code?](#how-do-you-avoid-deadlock-in-java-write-code-)
1. [ What is the difference between livelock and deadlock in Java?](#what-is-the-difference-between-livelock-and-deadlock-in-java-)
1. [How do you check if a Thread holds a lock or not?](#how-do-you-check-if-a-thread-holds-a-lock-or-not-)
1. [How do you take thread dump in Java?](#how-do-you-take-thread-dump-in-java-)
1. [Which JVM parameter is used to control stack size of a thread?](#which-jvm-parameter-is-used-to-control-stack-size-of-a-thread-)
1. [There are three threads T1, T2, and T3? How do you ensure sequence T1, T2, T3 in Java?](#there-are-three-threads-t1-t2-and-t3-how-do-you-ensure-sequence-t1-t2-t3-in-java-)
1. [What does yield method of Thread class do?](#what-does-yield-method-of-thread-class-do-)
1. [What is Semaphore in Java?](#what-is-semaphore-in-java-)
1. [What happens if you submit a task when the queue of the thread pool is already filled?](#what-happens-if-you-submit-a-task-when-the-queue-of-the-thread-pool-is-already-filled-)
1. [What is the difference between the volatile and atomic variable in Java?](#what-is-the-difference-between-the-volatile-and-atomic-variable-in-java-)
1. [What happens if a thread throws an Exception inside synchronized block?](#what-happens-if-a-thread-throws-an-exception-inside-synchronized-block-)
1. [List down 3 multi-threading best practice you follow?](#list-down-3-multi-threading-best-practice-you-follow-)
1. [What is false sharing in the context of multi-threading?](#what-is-false-sharing-in-the-context-of-multi-threading-)
1. [What is busy spin? Why should you use it?](#what-is-busy-spin-why-should-you-use-it-)

---

1. ##### What is Thread in Java? [&#10548;](#java-concurrency)

  The thread is an independent path of exercisecution. It's way to take advantage of multiple CPU available in a machine. By employing multiple threads you can speed up CPU bound task.

  For example, if one thread takes 100 milliseconds to do a job, you can use 10 thread to reduce that task into 10 milliseconds. Java provides excellent support for multi-threading at the language level, and it's also one of the strong selling points.

  [detail](http://java67.blogspot.com/2014/01/10-points-about-thread-and-javalangthread-in-java.html)

1. ##### Describe synchronization in respect to multi-threading. What is synchronization? [&#10548;](#java-concurrency)

  Several threads access common data.

  In order to keep the data in consistent state the access to it has to be synchronized (i.e. some ordering of data access has to be imposed).

2. ##### Explain different ways of using thread? [&#10548;](#java-concurrency)

  1. Create a long-running computation in a separate thread so the user interface (or whatever other part of the application) is not blocked.
  2. separate out I/O operations which potentially can take a lot of time (e.g. reading from the network) for the same reason
  3. process incoming requests in parallel (usually using thread pool of some size)
  4. Create thread to do some kind of isolated processing, wait for the processing to finish, kill the thread. Create new threads when needed

1. ##### How to stop a thread in Java? [&#10548;](#java-concurrency)

  I always said that Java provides rich APIs for everything but ironically Java doesn't provide a sure shot way of stopping thread.

  There was some control methods in JDK 1.0 e.g. stop(), suspend() and resume() which was deprecated in later releases due to potential deadlock threats, from then Java API designers has not made any effort to provide a consistent, thread-safe and elegant way to stop threads.

  Programmers mainly rely on the fact that thread stops automatically as soon as they finish execution of run() or call() method. To manually stop, programmers either take advantage of volatile boolean variable and check in every iteration if run method has loops or interrupt threads to abruptly cancel tasks.

  [detail/sample](http://javarevisited.blogspot.com/2011/10/how-to-stop-thread-java-example.html)

1. ##### What happens when an Exception occurs in a thread? [&#10548;](#java-concurrency)

  This is one of the good tricky Java question I have seen in interviews. In simple words, If not caught thread will die, if an uncaught exception handler is registered then it will get a call back.

  Thread.UncaughtExceptionHandler is an interface, defined as nested interface for handlers invoked when a Thread abruptly terminates due to an uncaught exception. When a thread is about to terminate due to an uncaught exception the Java Virtual Machine will query the thread for its UncaughtExceptionHandler using Thread.getUncaughtExceptionHandler() and will invoke the handler's uncaughtException() method, passing the thread and the exception as arguments.

1. ##### How do you share data between two thread in Java? [&#10548;](#java-concurrency)

  You can share data between threads by using shared object, or concurrent data structure like BlockingQueue. See this tutorial to learn  [inter-thread communication in Java](http://javarevisited.blogspot.sg/2013/12/inter-thread-communication-in-java-wait-notify-example.html). It implements Producer consumer pattern using wait and notify methods, which involves sharing objects between two threads.

  ![share-data-between-thread](https://2.bp.blogspot.com/-E9psXxo8Pjs/VuBAQ39X8JI/AAAAAAAAFCY/c__uJ2d3jwc/s1600/Inter%2Bthread%2BCommunication%2Bin%2BJava.jpg)

3. ##### What is the difference between preemptive scheduling and time slicing? [&#10548;](#java-concurrency)

  Not exactly a correct question.

  A scheduler can be preemptive (it's capable to force a process to interrupt its execution and resume it in some time) and non-preemptive (which is unable to interrupt a process and relies on the processes themselves that voluntarily give control to other tasks). Time slicing is a usual technique that is used in a preemptive multitasking system. The scheduler is run every time slice to choose the next process to run (it may happen that it's the same process during few time slices in a row, or it may happen that every time slice a different process is executed )

  To apply these terms to Java world -- replace the "process" with "thread", since the ideas behind scheduling processes in OS are the same as scheduling threads in an application.

4. ##### When a thread is created and started, what is its initial state? [&#10548;](#java-concurrency)

  The thread is then in **"RUNNABLE"** state.

1. ##### What is a thread local variable in Java? [&#10548;](#java-concurrency)
  Thread-local variables are variables confined to a thread, its like thread's own copy which is not shared between multiple threads. Java provides a ThreadLocal class to support thread-local variables. It's one of the many ways to achieve thread-safety.

  Though be careful while using thread local variable in manged environment e.g. with web servers where worker thread out lives any application variable. Any thread local variable which is not removed once its work is done can potentially cause a memory leak in Java application.

  ThreadLocal variables are special kind of variable available to Java programmer. Just like instance variable is per instance, ThreadLocal variable is per thread. It's a nice way to achieve thread-safety of expensive-to-create objects, for example you can make SimpleDateFormat thread-safe using ThreadLocal. Since that class is expensive, its not good to use it in local scope, which requires separate instance on each invocation. By providing each thread their own copy, you shoot two birds with one arrow. First, you reduce number of instance of expensive object by reusing fixed number of instances, and Second, you achieve thread-safety without paying cost of synchronization or immutability. Another good example of thread local variable is ThreadLocalRandom class, which reduces number of instances of expensive-to-create Random object in multi-threading environment.

  [detail](http://javarevisited.blogspot.sg/2012/05/how-to-use-threadlocal-in-java-benefits.html)

1. ##### When to use Runnable vs Thread in Java?

  As we know we can implement thread either by extending Thread class or implementing Runnable interface, the question arise, which one is better and when to use one?

  This question will be easy to answer if you know that Java programming language doesn't support multiple inheritances of class, but it allows you to implement multiple interfaces. Which means, it's better to implement Runnable then extends Thread if you also want to extend another class e.g. Canvas or CommandListener.

  [detail](http://javarevisited.blogspot.com/2012/01/difference-thread-vs-runnable-interface.html)

5. ##### Thread vs Runnable, run() vs start() [&#10548;](#java-concurrency)

  The main difference between run() and start() is that the latter creates a separate thread while the former executes the code synchronously

  One of trick Java question from early days, but still good enough to differentiate between shallow understanding of Java threading model start() method is used to start newly created thread, while start() internally calls run() method, there is difference calling run() method directly. When you invoke run() as normal method, its called in the same thread, no new thread is started, which is the case when you call start() method.

  [detail](http://javarevisited.blogspot.com/2012/03/difference-between-start-and-run-method.html)

6. ##### Describe different ways to create a thread. [&#10548;](#java-concurrency)

  1.
  ```
  class MyRunnable extends SomeOtherClass implements Runnable {
      public void run(){
          // code that has to run in a thread
      }
  }

  MyRunnable r = new MyRunnable();
  Thread t = new Thread(r);
  r.start();
  ```

  2.
  ```
  class MyThread extends Thread {
      public void run(){
          // code that has to run in a thread
      }
  }

  Thread t = new MyThred();
  t.start();
  ```
  3.
  ```
  class MySomething extends Something {
      public void doSomeStuff() {...}
  }

  new Thread(new Runnable() {
      public void run(){
          instanceOfMySomething.doSomeStuff();
      }
  }).start();
  ```

  The main difference between these two approaches is that:
  * In case (1) you are able to extend the class you need while still being able to run your code in a separate thread.
  * In case (2) you are already extending from the Thread class which limits your options. In general following one of the good OOP practices (Favor composition over inheritance) option (a) is preferable.
  * Option (3) is also cute since it decouples your class and the fact that its code will be run in a separate thread. In other words you can still call instanceOfMySomething.doSomeStuff() regardless from a new thread or from the same.

  Another answer is:

  At the language level, there are two ways to implement Thread in Java. An instance of java.lang.Thread represent a thread but it needs a task to execute, which is an instance of interface java.lang.Runnable. Since Thread class itself implement Runnable, you can override run() method either by extending Thread class or just implementing Runnable interface.

  [detail](http://javarevisited.blogspot.com/2011/02/how-to-implement-thread-in-java.html)

7. ##### Synchronization of Java blocks and methods [&#10548;](#java-concurrency)

  Methods declared synchronized and statements contained in synchronized blocks. Only one thread is allowed to be executing instructions inside a synchronized block.

  The main difference between *synchronized block* and *synchronized method* is that you can choose which object will be used for synchronization in case of blocks. The methods are always synchronized with "this"

8. ##### Explain usage of the couple wait()/notify() [&#10548;](#java-concurrency)

  The mechanism is used to allow one thread to signal another. E.g. Consumer signals that he's waiting for the next object to process, or Producer signals that a new object is ready to be processed.

  * wait( ) tells the calling thread to give up the monitor and go to sleep until some other thread enters the same monitor and calls notify( ).
  * notify( ) wakes up the a thread (a random one?) that called wait( ) on the same object.
  * notifyAll( ) wakes up all the threads that called wait( ) on the same object.

1. ##### Why wait and notify method are called from synchronized block? [&#10548;](#java-concurrency)

  Main reason for calling wait and notify method from either synchronized block or method is that it made mandatory by Java API. If you don't call them from synchronized context, your code will throw IllegalMonitorStateException. A more subtle reason is to avoid the race condition between wait and notify calls.

  [detail](http://javarevisited.blogspot.com/2011/05/wait-notify-and-notifyall-in-java.html)

1. ##### What is the difference between notify and notifyAll in Java? [&#10548;](#java-concurrency)

  This is another tricky questions from core Java interviews. Since multiple threads can wait on single monitor lock, Java API designer provides method to inform only one of them or all of them, once waiting condition changes, but they provide half implementation.

  There notify() method doesn't provide any way to choose a particular thread, that's why its only useful when you know that there is only one thread is waiting.

  On the other hand, notifyAll() sends notification to all threads and allows them to compete for locks, which ensures that at-least one thread will proceed further. See this [blog post](http://javarevisited.blogspot.com/2012/10/difference-between-notify-and-notifyall-java-example.html) on similar topic for a more detailed answer and code example.

1. ##### Why wait, notify and notifyAll are not inside thread class? [&#10548;](#java-concurrency)

  This is a design related question, which checks what candidate thinks about existing system or does he ever thought of something which is so common but looks in-appropriate at first.

  In order to answer this question, you have to give some reasons why it make sense for these three method to be in Object class, and why not on Thread class.

  One reason which is obvious is that Java provides lock at object level not at thread level. Every object has lock, which is acquired by thread. Now if thread needs to wait for certain lock it make sense to call wait() on that object rather than on that thread. Had wait() method declared on Thread class, it was not clear that for which lock thread was waiting.

  In short, since wait, notify and notifyAll operate at lock level, it make sense to defined it on object class because lock belongs to object. You can also see [this article](http://javarevisited.blogspot.sg/2012/02/why-wait-notify-and-notifyall-is.html) for more elaborate answer of this question.

  [detail](http://java67.blogspot.com/2013/03/difference-between-wait-vs-notify-vs-notifyAll-java-thread.html)

1. ##### How do you call wait() method? using if block or loop? Why? [&#10548;](#java-concurrency)
  wait() method should always be called in loop because it's possible that until thread gets CPU to start running again the condition might not hold, so its always better to check condition in loop before proceeding. Here is the standard idiom of using wait and notify method in Java:

  ```
  // The standard idiom for using the wait method
  synchronized (obj) {
     while (condition does not hold)
        obj.wait(); // (Releases lock, and reacquires on wakeup)
        ... // Perform action appropriate to condition
  }
  ```
  See [Effective Java Item 69](http://www.amazon.com/dp/0321356683/?tag=javamysqlanta-20) to learn more about why wait method should call in the loop

1. ##### What are differences between wait and sleep method in Java? [&#10548;](#java-concurrency)

  Though both are used to pause currently running thread.

  * sleep() is actually meant for short pause because it doesn't release lock.
  * while wait() is meant for conditional wait and that's why it release lock which can then be acquired by another thread to change the condition on which it is waiting.

9. ##### What does Volatile keyword mean? [&#10548;](#java-concurrency)

  We typically use volatile keyword when we share variables with more than one thread in a multi-threaded environment, and we want to avoid any memory inconsistency errors due to the caching of these variables in the CPU cache.

  The **volatile** keyword guarantees that reads and from a variable will see the changes made by the last write to this variable (and of course all other writes that happened earlier).

  Java documentation states that volatile establishes a "happens-before" relationship between a write to a variable and all subsequent reads from it.

  ***What is a Happens-before Relationship?***

  A happens-before relationship between two program statements is sort a guarantee which ensures that any memory writes by one statement are visible to another statement.

  ![java-memory](http://3.bp.blogspot.com/-o2VBopq_Bcc/VKAXLDExe9I/AAAAAAAACTM/KtLZB1WVBGk/s1600/volatile%2Bvariable%2Bin%2BJava.png)

  ***When to use Volatile variable in Java?***

  * Any variables which is shared between multiple threads should be made volatile, in order to ensure that all threads must see the latest value of volatile variable.
  * A signal to compiler and JIT to ensure that compiler does not change ordering or volatile variable and moves them out of synchronized context.
  * You want to save the cost of synchronization as volatile variables are less expensive than synchronization.
  * Another place where a volatile variable can be used is to fixing double checked locking in Singleton pattern

  ***More details*** : [javarevisited](http://javarevisited.blogspot.com/2011/06/volatile-keyword-java-example-tutorial.html) (\*) , [dzone](https://dzone.com/articles/java-multi-threading-volatile-variables-happens-be-1)(\*), [mechanical-sympathy](http://mechanical-sympathy.blogspot.fr/2013/02/cpu-cache-flushing-fallacy.html), [jpbempel](http://jpbempel.blogspot.fr/2012/10/volatile.html), [java67](http://java67.blogspot.com/2012/08/what-is-volatile-variable-in-java-when.html)

10. ##### Difference between synchronized and volatile keyword in Java? [&#10548;](#java-concurrency)

  Remember volatile is not a replacement of synchronized keyword but can be used as an alternative in certain cases. Here are few differences between volatile and synchronized keyword in Java.

  1. The volatile keyword in Java is a field modifier while synchronized modifies code blocks and methods.

  2. Synchronized obtains and releases the lock on monitor’s Java volatile keyword doesn't require that.

  3. Threads in Java can be blocked for waiting for any monitor in case of synchronized, that is not the case with the volatile keyword in Java.

  4. Synchronized method affects performance more than a volatile keyword in Java.

  5. Since volatile keyword in Java only synchronizes the value of one variable between Thread memory and "main" memory while synchronized synchronizes the value of all variable between thread memory and "main" memory and locks and releases a monitor to boot. Due to this reason synchronized keyword in Java is likely to have more overhead than volatile.

  6. You can not synchronize on the null object but your volatile variable in Java could be null.

  7. From Java 5 writing into a volatile field has the same memory effect as a monitor release, and reading from a volatile field has the same memory effect as a monitor acquire

1. ##### The difference between Serializable and Externalizable in Java? [&#10548;](#java-concurrency)

  This is one of the frequently asked questions from Java Serialization. The interviewer has been asking this question since the day Serialization was introduced in Java, but yet only a few good candidate can answer this question with some confidence and practical knowledge.

  Serializable interface is used to make Java classes serializable so that they can be transferred over network or their state can be saved on disk, but it leverages default serialization built-in JVM, which is expensive, fragile and not secure. Externalizable allows you to fully control the Serialization process, specify a custom binary format and add more security measure.

  [detail](http://javarevisited.blogspot.sg/2012/01/serializable-externalizable-in-java.html)

10. ##### java.util.concurrent.* , what utils do you know? [&#10548;](#java-concurrency)

  * Synchronization primitives: Semaphore, CyclicBarrier, CountDownLatch, Lock, ReentrantLock
  * Threads: Executors, Callable and Future
  * Data: Synchronized collections (CopyOnWriteArrayList, ConcurrentHashMap, BlockingQueue)

11. ##### ThreadLocal, what for are they needed? Does child thread see the value of parent ThreadLocal? [&#10548;](#java-concurrency)

  Values stored in Thread Local are global to the thread, meaning that they can be accessed from anywhere inside that thread. If a thread calls methods from several classes, then all the methods can see the Thread Local variable set by other methods (because they are executing in same thread). The value need not be passed explicitly. It’s like how you use global variables.

  One possible (and common) use is when you have some object that is not thread-safe, but you want to avoid synchronizing access to that object. Instead, give each thread its own instance of the object. ThreadLocals are one sort of global variables (although slightly less evil because they are restricted to one thread), so you should be careful when using them to avoid unwanted side-effects and memory leaks. Design your APIs so that the ThreadLocal values will always be automatically cleared when they are not anymore needed and that incorrect use of the API won't be possible (for example like this).

  No. The child thread doesn't see the value of parent ThreadLocal unless InheritableThreadLocal<T> is used.

12. ##### Recommendations to avoid deadlocks. [&#10548;](#java-concurrency)

  1. We may create a class that will register all locks being held by all the threads. Thus before granting a new lock to a thread we may check whether it will not lead to a deadlock and grant the lock only if it doesn't.
  2. We may devise a policy of acquiring the locks by the threads that will guarantee a deadlock-free program. A simple example of such policy is: no thread is allowed to have more than one lock at a time.

13. ##### What is daemon thread and which method is used to create the daemon thread? [&#10548;](#java-concurrency)

  A daemon thread is a thread, that does not prevent the JVM from exiting when the program finishes but the thread is still running.

  An example for a daemon thread is the garbage collection.

  The setDaemon() method can be used to change the Thread daemon properties.

  Normal thread and daemon threads differ in what happens when they exit. When the JVM halts any remaining daemon threads are abandoned: finally blocks are not executed, stacks are not unwound - JVM just exits. Due to this reason daemon threads should be used sparingly and it is dangerous to use them for tasks that might perform any sort of I/O.

14. ##### What method must be implemented by all threads? [&#10548;](#java-concurrency)

  run(); by default (in the Thread class itself) it does nothing and returns

15. ##### What is the difference between process and thread? [&#10548;](#java-concurrency)

  From Java documentation: A process has a self-contained execution environment. A process generally has a complete, private set of basic run-time resources; in particular, each process has its own memory space. Most implementations of the Java virtual machine run as a single process

  Threads are sometimes called lightweight processes. Both processes and threads provide an execution environment, but creating a new thread requires fewer resources than creating a new process. Threads exist within a process - every process has at least one. Threads share the process's resources, including memory and open files. This makes for efficient, but potentially problematic, communication.

  Two process runs on different memory space, but all threads share same memory space.

  Don't confuse this with stack memory, which is different for the different thread and used to store local data to that thread. For more detail see the answer.

  [detail_1](http://java67.blogspot.com/2012/12/what-is-difference-between-thread-vs-process-java.html), [detail_2](http://javarevisited.blogspot.sg/2015/12/difference-between-thread-and-process.html)

1. ##### What is an immutable object? How do you create an Immutable object in Java? [&#10548;](#java-concurrency)

  Immutable objects are those whose state cannot be changed once created.

  Any modification will result in a new object e.g. String, Integer, and other wrapper class. Please see the answer for step by step guide to creating Immutable class in Java.

  ***References:*** [javarevisited](http://javarevisited.blogspot.sg/2013/03/how-to-create-immutable-class-object-java-example-tutorial.html)

1. Can we create an Immutable object, which contains a mutable object? [&#10548;](#java-concurrency)
  Yes, its possible to create an Immutable object which may contain a mutable object, you just need to be a little bit careful not to share the reference of the mutable component, instead, you should return a copy of it if you have to. Most common example is an Object which contain the reference of java.util.Date object.

16. ##### What are the states associated in the thread? [&#10548;](#java-concurrency)

17. ##### When you will synchronize a piece of your code? [&#10548;](#java-concurrency)

  Whenever there will be a need: most probably when there will be concurrent access to some data

18. ##### What is deadlock? Example of deadlock. [&#10548;](#java-concurrency)

  Deadlock is a state in which some threads of an application (at least two threads) are mutually blocked (A waits for resource X held by B, while B waits for resource Y held by A). Neither can continue in this case. Note that only part of application can be in a deadlock state while other thread continue their execution.

  ```
  public class DeadlockTest {
  public static void main(String[] args) {

      String s1 = "S1";
      String s2 = "S2";

      Thread t1 = new Thread(new DeadlockCause(s1, s2));
      Thread t2 = new Thread(new DeadlockCause(s2, s1));

      t1.start();
      t2.start();

      }
  }

  class DeadlockCause implements Runnable {

      private final Object firstLock;
      private final Object secondLock;

      public DeadlockCause(Object o1, Object o2) {
          firstLock = o1;
          secondLock = o2;
      }

      @Override
      public void run() {
          synchronized(firstLock){
              System.out.println(Thread.currentThread().getName() +  " holds the lock on " + firstLock);
              try {
                  Thread.sleep(1000);
              } catch (InterruptedException ex) {
                  Logger.getLogger(DeadlockCause.class.getName()).log(Level.SEVERE, null, ex);
              }

              System.out.println(Thread.currentThread().getName() +  " tries to get the lock on " + secondLock);
              synchronized(secondLock){
                  System.out.println(Thread.currentThread().getName() +  " holds the lock on " + secondLock);
              }
          }
      }
  }
  ```

19. ##### Are there any global variables in Java, which can be accessed by other part of your program? [&#10548;](#java-concurrency)

  No, there are no global variables in Java.

20. ##### What are Callable and FutureTask interfaces? [&#10548;](#java-concurrency)

  Motivation to create: with Thread and Runnable you cannot return a value as the result of executing the task. Additionally you have to process all the exception inside the run() method because its declaration is public void run() and doesn't allow exceptions to be thrown.

  The Callable has the method public T call() throws Exception. When an ExecutorService gets submitted a Callable<T> it returns a Future<T>. The get() method on this Future<T> instance has to be called in order to get the result.

  Example:

  ```
   ExecutorService executor = Executors.newFixedThreadPool();
   Future<Integer> future = executor.submit(new Callable<Integer>(){
       public Integer call() throws Exception {
           Integer result = 0;
           // do some stuff here
           return result;
       }
   });

   executor.shutdown(); // stop accepting new tasks

   try {
       System.out.println("The result is: " + future.get());
   } catch (InterruptedException ex) {
       ...
   }
  ```

  **What is FutureTask in Java?**

  FutureTask represents a cancellable asynchronous computation in concurrent Java application. This class provides a base implementation of Future, with methods to start and cancel a computation, query to see if the computation is complete, and retrieve the result of the computation. The result can only be retrieved when the computation has completed; the get methods will block if the computation has not yet completed. A FutureTask object can be used to wrap a Callable or Runnable object. Since FutureTask also implements Runnable, it can be submitted to an Executor for execution.

1. ##### What is the difference between the interrupted() and isInterrupted() method in Java?

  Main difference between interrupted() and isInterrupted() is that former clears the interrupt status while later does not. The interrupt mechanism in Java multi-threading is implemented using an internal flag known as the interrupt status. Interrupting a thread by calling Thread.interrupt() sets this flag. When interrupted thread checks for an interrupt by invoking the static method Thread.interrupted(), interrupt status is cleared. The non-static isInterrupted() method, which is used by one thread to query the interrupt status of another, does not change the interrupt status flag. By convention, any method that exits by throwing an InterruptedException clears interrupt status when it does so. However, it's always possible that interrupt status will immediately be set again, by another thread invoking interrupt.

1. ##### What is the difference between Runnable and Callable in Java? [&#10548;](#java-concurrency)

  Both Runnable and Callable represent task which is intended to be executed in a separate thread.

  Runnable is there from JDK 1.0 while Callable was added on JDK 1.5.

  Main difference between these two is that Callable's call() method can return value and throw Exception, which was not possible with Runnable's run() method. Callable return Future object, which can hold the result of computation.

  [detail](http://java67.blogspot.com/2013/01/difference-between-callable-and-runnable-java.html)

1. ##### What is the difference between CyclicBarrier and CountDownLatch in Java? [&#10548;](#java-concurrency)

  Though both CyclicBarrier and CountDownLatch wait for number of threads on one or more events, the main difference between them is that you can not re-use CountDownLatch once count reaches to zero, but you can reuse same CyclicBarrier even after barrier is broken.

  [detail](http://javarevisited.blogspot.com/2012/07/cyclicbarrier-example-java-5-concurrency-tutorial.html)

1. ##### What is thread-safety? Is Vector a thread-safe class? [&#10548;](#java-concurrency)

  Thread-safety is a property of an object or code which guarantees that if executed or used by multiple threads in any manner e.g. read vs write it will behave as expected. For example, a thread-safe counter object will not miss any count if same instance of that counter is shared among multiple threads.

  Apparently, you can also divide collection classes in two category, thread-safe and non-thread-safe. Vector is indeed a thread-safe class and it achieves thread-safety by synchronizing methods which modify state of Vector, on the other hand, its counterpart ArrayList is not thread-safe.

  [detail](http://javarevisited.blogspot.sg/2011/09/difference-vector-vs-arraylist-in-java.html)

1. ##### What is race condition in Java? Given one example? [&#10548;](#java-concurrency)

  Race condition are cause of some subtle programming bugs when Java programs are exposed to concurrent execution environment. As the name suggests, a race condition occurs due to race between multiple threads, if a thread which is supposed to execute first lost the race and executed second, behavior of code changes, which surface as non-deterministic bugs. This is one of the hardest bugs to find and re-produce because of random nature of racing between threads. One example of race condition is out-of-order processing, see this answer for some more example of race conditions in Java programs.

  [detail](http://javarevisited.blogspot.com/2012/02/what-is-race-condition-in.html)

1. ##### What is Java Memory model? [&#10548;](#java-concurrency)

  Java Memory model is set of rules and guidelines which allows Java programs to behave deterministically across multiple memory architecture, CPU, and operating system. It's particularly important in case of multi-threading. Java Memory Model provides some guarantee on which changes made by one thread should be visible to others, one of them is happens-before relationship. This relationship defines several rules which allows programmers to anticipate and reason behavior of concurrent Java programs. For example, happens-before relationship guarantees :

  * Each action in a thread happens-before every action in that thread that comes later in the program order, this is known as program order rule.
  * An unlock on a monitor lock happens-before every subsequent lock on that same monitor lock, also known as Monitor lock rule.
  * A write to a volatile field happens-before every subsequent read of that same field, known as Volatile variable rule.
  * A call to Thread.start on a thread happens-before any other thread detects that thread has terminated, either by successfully return from Thread.join() or by Thread.isAlive() returning false, also known as Thread start rule.
  * A thread calling interrupt on another thread happens-before the interrupted thread detects the interrupt (either by having InterruptedException thrown, or invoking isInterrupted or interrupted), popularly known as Thread Interruption rule.
  * The end of a constructor for an object happens-before the start of the finalizer for that object, known as Finalizer rule.
  * If A happens-before B, and B happens-before C, then A happens-before C, which means happens-before guarantees Transitivity.

  Advise: read chap 16 of "Java concurrency in practice"

21. ##### What is Executors framework? [&#10548;](#java-concurrency)

  [Oracle_JavaSE](http://docs.oracle.com/javase/tutorial/essential/concurrency/exinter.html)

22. ##### What is AtomicInteger [&#10548;](#java-concurrency)

  AtomicInteger is a class from java.util.concurrent package that provides thread-safe implementation of an Integer.

  More information on AtomicXXX can be found at [Oracle_JavaSE](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/atomic/package-summary.html)

1. ##### Why should you check condition for waiting in a loop? [&#10548;](#java-concurrency)

  Its possible for a waiting thread to receive false alerts and spurious wake up calls, if it doesn't check the waiting condition in loop, it will simply exit even if condition is not met. As such, when a waiting thread wakes up, it cannot assume that the state it was waiting for is still valid. It may have been valid in the past, but the state may have been changed after the notify() method was called and before the waiting thread woke up. That's why it always better to call wait() method from loop, you can even create template for calling wait and notify in Eclipse. To learn more about this question, I would recommend you to read Effective Java items on thread and synchronization.

  [detail](http://javarevisited.blogspot.com/2015/07/how-to-use-wait-notify-and-notifyall-in.html)

1. ##### What is the difference between synchronized and concurrent collection in Java? [&#10548;](#java-concurrency)

	Though both synchronized and concurrent collection provides thread-safe collection suitable for multi-threaded and concurrent access, later is more scalable than former. Before Java 1.5, Java programmers only had synchronized collection which becomes source of contention if multiple thread access them concurrently, which hampers scalability of system.
	
	Java 5 introduced concurrent collections like ConcurrentHashMap, which not only provides thread-safety but also improves scalability by using modern techniques like lock stripping and partitioning internal table.

	[detail](http://javarevisited.blogspot.com/2010/10/what-is-difference-between-synchronized.html) 

1. ##### What is the difference between Stack and Heap in Java? [&#10548;](#java-concurrency)

	Why does someone this question as part of multi-threading and concurrency? Because Stack is a memory area which is closely associated with threads.
	
	To answer this question, both stack and heap are specific memories in Java application. Each thread has their own stack, which is used to store local variables, method parameters and call stack. 
	
	Variable stored in one Thread's stack is not visible to other. On another hand, the heap is a common memory area which is shared by all threads.
	
	Objects whether local or at any level is created inside heap. To improve performance thread tends to cache values from heap into their stack, which can create problems if that variable is modified by more than one thread, this is where volatile variables come into the picture. volatile suggest threads read the value of variable always from main memory.
	
	![stack_and_heap](https://3.bp.blogspot.com/-vJvHCwr7ozY/VuBB4nlNpkI/AAAAAAAAFCk/8mqWs5unUK4/s400/Heap%2Bvs%2BStack%2Bin%2BJava.jpg)
	
	[detail](http://javarevisited.blogspot.com/2013/01/difference-between-stack-and-heap-java.html)

1. ##### What is thread pool? Why should you thread pool in Java? [&#10548;](#java-concurrency)

	Creating thread is expensive in terms of time and resource. If you create thread at time of request processing it will slow down your response time, also there is only a limited number of threads a process can create.
	
	To avoid both of these issues, a pool of thread is created when application starts-up and threads are reused for request processing. This pool of thread is known as "thread pool" and threads are known as worker thread.
	
	From JDK 1.5 release, Java API provides Executor framework, which allows you to create different types of thread pools e.g. single thread pool, which process one task at a time, fixed thread pool (a pool of fixed number of threads) or cached thread pool (an expandable thread pool suitable for applications with many short lived tasks).
	
	[detail](http://javarevisited.blogspot.com/2013/07/how-to-create-thread-pools-in-java-executors-framework-example-tutorial.html)

1. ##### Write code to solve Producer Consumer problem in Java? [&#10548;](#java-concurrency)

	Most of the threading problem you solved in the real world are of the category of Producer consumer pattern, where one thread is producing task and another thread is consuming that. You must know how to do inter thread communication to solve this problem. At the lowest level, you can use wait and notify to solve this problem, and at a high level, you can leverage Semaphore or BlockingQueue to implement Producer consumer pattern, as shown in this [tutorial](http://javarevisited.blogspot.sg/2012/02/producer-consumer-design-pattern-with.html).

	[detail](http://java67.blogspot.com/2015/12/producer-consumer-solution-using-blocking-queue-java.html)

1. ##### How do you avoid deadlock in Java? Write Code? [&#10548;](#java-concurrency)

	![deadlock](http://4.bp.blogspot.com/-m2IldPcxiJI/U6-Zwvkdd1I/AAAAAAAABns/-zHIHjzM3nM/s1600/deadlock+in+Java.jpg)

	Deadlock is a condition in which two threads wait for each other to take action which allows them to move further. It's a serious issue because when it happen your program hangs and doesn't do the task it is intended for. In order for deadlock to happen, following four conditions must be true:

	* Mutual Exclusion : At least one resource must be held in a non-shareable mode. Only one process can use the resource at any given instant of time.
	* Hold and Wait: A process is currently holding, at least, one resource and requesting additional resources which are being held by other processes.
	* No Pre-emption: The operating system must not de-allocate resources once they have been allocated; they must be released by the holding process voluntarily.
	* Circular Wait: A process must be waiting for a resource which is being held by another process, which in turn is waiting for the first process to release the resource.

	The easiest way to avoid deadlock is to prevent *Circular wait*, and this can be done by acquiring locks in a particular order and releasing them in reverse order so that a thread can only proceed to acquire a lock if it held the other one. Check this tutorial for the actual code example and detailed discussion on techniques for avoiding deadlock in Java.
	
1. ##### What is the difference between livelock and deadlock in Java? [&#10548;](#java-concurrency)

	This question is extension of previous interview question. A livelock is similar to a deadlock, except that the states of the threads or processes involved in the livelock constantly change with regard to one another, without any one progressing further. Livelock is a special case of resource starvation.
	
	A real-world example of livelock occurs when two people meet in a narrow corridor, and each tries to be polite by moving aside to let the other pass, but they end up swaying from side to side without making any progress because they both repeatedly move the same way at the same time.
	
	In short, the main difference between livelock and deadlock is that in former state of process change but no progress is made.

1. ##### How do you check if a Thread holds a lock or not? [&#10548;](#java-concurrency)

	I didn't even know that you can check if a Thread already holds lock before this question hits me in a telephonic round of Java interview.
	
	There is a method called holdsLock() on java.lang.Thread, it returns true if and only if the current thread holds the monitor lock on the specified object.

	[detail](http://javarevisited.blogspot.com/2010/10/how-to-check-if-thread-has-lock-on.html)

1. ##### How do you take thread dump in Java? [&#10548;](#java-concurrency)

	There are multiple ways to take thread dump of Java process depending upon operating system. When you take thread dump, JVM dumps state of all threads in log files or standard error console. In windows you can use *Ctrl + Break* key combination to take thread dump, on Linux you can use *kill -3* command for same. You can also use a tool called *jstack* for taking thread dump, it operate on process id, which can be found using another tool called *jps*.
	
	[detail](http://javarevisited.blogspot.com/2011/07/java-multi-threading-interview.html)
	
1. ##### Which JVM parameter is used to control stack size of a thread? [&#10548;](#java-concurrency)

	This is the simple one, -Xss parameter is used to control stack size of Thread in Java. You can see this [list of JVM](http://javarevisited.blogspot.com/2011/11/hotspot-jvm-options-java-examples.html) options to learn more about this parameter.

1. ##### There are three threads T1, T2, and T3? How do you ensure sequence T1, T2, T3 in Java? [&#10548;](#java-concurrency)

	Sequencing in multi-threading can be achieved by different means but you can simply use the **join()** method of thread class to start a thread when another one has finished its execution. To ensure three threads execute you need to start the last one first e.g. T3 and then call join methods in reverse order e.g. T3 calls T2. join and T2 calls T1.join, these ways T1 will finish first and T3 will finish last. To learn more about join method, see this [tutorial](http://javarevisited.blogspot.sg/2013/02/how-to-join-multiple-threads-in-java-example-tutorial.html).

1. ##### What does yield method of Thread class do? [&#10548;](#java-concurrency)

	Yield method is one way to request current thread to relinquish CPU so that other thread can get a chance to execute. Yield is a static method and only guarantees that current thread will relinquish the CPU but doesn't say anything about which other thread will get CPU. Its possible for the same thread to get CPU back and start its execution again.

	[detail](http://java67.blogspot.sg/2012/08/difference-between-yield-and-wait.html)

1. ##### What is Semaphore in Java? [&#10548;](#java-concurrency)

	Semaphore in Java is a new kind of synchronizer. It's a counting semaphore.
	
	Conceptually, a semaphore maintains a set of permits. Each acquire() blocks if necessary until a permit is available, and then takes it.
	
	Each release() adds a permit, potentially releasing a blocking acquirer. However, no actual permit objects are used; the Semaphore just keeps a count of the number available and acts accordingly. 
	
	Semaphore is used to protect an expensive resource which is available in fixed number e.g. database connection in the pool.
	
	[detail](http://javarevisited.blogspot.com/2012/05/counting-semaphore-example-in-java-5.html)

1. ##### What happens if you submit a task when the queue of the thread pool is already filled? [&#10548;](#java-concurrency)

	This is another tricky question on my list. Many programmers will think that it will block until a task is cleared but its true. *ThreadPoolExecutor*'s *submit()* method throws *RejectedExecutionException* if the task cannot be scheduled for execution.

1. ##### What is the difference between the volatile and atomic variable in Java? [&#10548;](#java-concurrency)

	This is an interesting question for Java programmer, at first, volatile and atomic variable look very similar, but they are different.
	
	Volatile variable provides you happens-before guarantee that a write will happen before any subsequent write, it doesn't guarantee atomicity. For example count++ operation will not become atomic just by declaring count variable as volatile.
	
	On the other hand *AtomicInteger* class provides atomic method to perform such compound operation atomically e.g. *getAndIncrement()* is atomic replacement of increment operator. It can be used to atomically increment current value by one. Similarly you have atomic version for other data type and reference variable as well.

1. ##### What happens if a thread throws an Exception inside synchronized block? [&#10548;](#java-concurrency)

	This is one more tricky question for average Java programmer, if he can bring the fact about whether lock is released or not is a key indicator of his understanding.
	
	To answer this question, no matter how you exist synchronized block, either normally by finishing execution or abruptly by throwing exception, thread releases the lock it acquired while entering that synchronized block. This is actually one of the reasons I like synchronized block over lock interface, which requires explicit attention to release lock, generally this is achieved by releasing the lock in a [finally block](http://javarevisited.blogspot.com/2012/11/difference-between-final-finally-and-finalize-java.html).

1. ##### List down 3 multi-threading best practice you follow? [&#10548;](#java-concurrency)

	This is my favorite question because I believe that you must follow certain best practices while writing concurrent code which helps in performance, debugging and maintenance. Following are three best practices, I think an average Java programmer should follow:
	
	* **Always give meaningful name to your thread** This goes a long way to find a bug or trace an execution in concurrent code. *OrderProcessor, QuoteProcessor* or *TradeProcessor* is much better than Thread-1. Thread-2 and Thread-3. The name should say about task done by that thread. All major framework and even JDK follow this best practice.
	* **Avoid locking or Reduce scope of Synchronization** Locking is costly and context switching is even costlier. Try to avoid synchronization and locking as much as possible and at a bare minimum, you should reduce critical section. That's why I prefer synchronized block over synchronized method because it gives you absolute control on the scope of locking.
	* **Prefer Synchronizers over wait and notify** Synchronizers like *CountDownLatch, Semaphore, CyclicBarrier* or *Exchanger* simplifies coding. It's very difficult to implement complex control flow right using wait and notify. Secondly, these classes are written and maintained by best in business and there is good chance that they are optimized or replaced by better performance code in subsequent JDK releases. By using higher level synchronization utilities, you automatically get all these benefits.
	* **Prefer Concurrent Collection over Synchronized Collection** This is another simple best practice which is easy to follow but reap good benefits. Concurrent collection are more scalable than their synchronized counterpart, that's why its better to use them while writing concurrent code. So next time if you need map, think about *ConcurrentHashMap* before thinking *Hashtable*. See my article [Concurrent Collections in Java](http://javarevisited.blogspot.com/2013/02/concurrent-collections-from-jdk-56-java-example-tutorial.html), to learn more about modern collection classes and how to make best use of them.

	[more](http://javarevisited.blogspot.com/2015/05/top-10-java-multithreading-and.html)

1. ##### What is false sharing in the context of multi-threading? [&#10548;](#java-concurrency)

	false sharing is one of the well-known performance issues on multi-core systems, where each process has its local cache. false sharing occurs when threads on different processor modify variables that reside on same cache line as shown in the following image:

	![false-sharing](https://2.bp.blogspot.com/-Tze9foqpb74/VepwCzXHGCI/AAAAAAAADtM/i4KQDaefqk4/s400/False%2BSharing%2Bin%2BMulti-threaded%2Bapplication.gif)
	
	False sharing is very hard to detect because the thread may be accessing completely different global variables that happen to be relatively close together in memory. Like many concurrency issues, the primary way to avoid false sharing is careful code review and aligning your data structure with the size of a cache line.

	[detail](http://mechanical-sympathy.blogspot.com/2011/07/false-sharing.html)

1. ##### What is busy spin? Why should you use it? [&#10548;](#java-concurrency)

	Busy spin is one of the technique (*waiting strategy*) to wait for events without releasing CPU.
	
	It's often done to avoid losing data in CPU cached which is lost if the thread is paused and resumed in some other core.
	
	So, if you are working on low latency system where your order processing thread currently doesn't have any order, instead of sleeping or calling wait(), you can just loop and then again check the queue for new messages.
	
	It's only beneficial if you need to wait for a very small amount of time e.g. in micro seconds or nano seconds.
	
	[LMAX Disrupter](http://lmax-exchange.github.io/disruptor/) framework, a high-performance inter-thread messaging library has a BusySpinWaitStrategy which is based on this concept and uses a busy spin loop for EventProcessors waiting on the barrier.

Tutorial
---

1. [Java Concurrency - vogella](http://www.vogella.com/tutorials/JavaConcurrency/article.html)
2. [Java Concurrency - jenkov](http://tutorials.jenkov.com/java-concurrency/index.html)

References
---
* [original-aticle](https://github.com/svozniuk/java-interviews/blob/master/Java%20Core/Java%20Concurrency.txt)

* [need-translate-top50q](http://www.duct-tape-architect.ru/?p=294)

* [javarevisited-top50q](http://javarevisited.blogspot.com/2014/07/top-50-java-multithreading-interview-questions-answers.html)

* [javarevisited-top15q](http://javarevisited.blogspot.com/2011/07/java-multi-threading-interview.html)

* [javacodegeeks-84q](https://www.javacodegeeks.com/2014/11/multithreading-concurrency-interview-questions-answers.html)

* [java67-top12q](http://java67.blogspot.com/2012/08/5-thread-interview-questions-answers-in.html)

* [dzone-top80q](https://dzone.com/articles/threads-top-80-interview)

* [journaldev](http://www.journaldev.com/1162/java-multi-threading-concurrency-interview-questions-with-answers)

[top](#java-concurrency)
