Java Concurrency
---

List questions:

1. [Describe synchronization in respect to multi-threading. What is synchronization?](#describe-synchronization-in-respect-to-multi-threading-what-is-synchronization-)
1. [Explain different ways of using thread?](#explain-different-ways-of-using-thread-)
1. [What is the difference between preemptive scheduling and time slicing?](#what-is-the-difference-between-preemptive-scheduling-and-time-slicing-)
1. [When a thread is created and started, what is its initial state?](#when-a-thread-is-created-and-started-what-is-its-initial-state-)
1. [Thread vs Runnable, run() vs start()](#thread-vs-runnable-run-vs-start-)
1. [Describe different ways to create a thread.](#describe-different-ways-to-create-a-thread-)
1. [Synchronization of Java blocks and methods](#synchronization-of-java-blocks-and-methods-)
1. [Explain usage of the couple wait()/notify()](#explain-usage-of-the-couple-waitnotify-)
1. [What does Volatile keyword mean?](#what-does-volatile-keyword-mean-)
1. [Difference between synchronized and volatile keyword in Java](#difference-between-synchronized-and-volatile-keyword-in-java-)
1. [java.util.concurrent.* , what utils do you know?](#javautilconcurrent--what-utils-do-you-know-)
1. [ThreadLocal, what for are they needed? Does child thread see the value of parent ThreadLocal?](#threadlocal-what-for-are-they-needed-does-child-thread-see-the-value-of-parent-threadlocal-)
1. [Recommendations to avoid deadlocks.](#recommendations-to-avoid-deadlocks-)
1. [What is daemon thread and which method is used to create the daemon thread?](#what-is-daemon-thread-and-which-method-is-used-to-create-the-daemon-thread-)
1. [What method must be implemented by all threads?](#what-method-must-be-implemented-by-all-threads-)
1. [What is the difference between process and thread?](#what-is-the-difference-between-process-and-thread-)
1. What are the states associated in the thread?
1. [When you will synchronize a piece of your code?](#when-you-will-synchronize-a-piece-of-your-code-)
1. [What is deadlock? Example of deadlock.](#what-is-deadlock-example-of-deadlock-)
1. [Are there any global variables in Java, which can be accessed by other part of your program?](#are-there-any-global-variables-in-java-which-can-be-accessed-by-other-part-of-your-program-)
1. [What are Callable and FutureTask interfaces?](#what-are-callable-and-futuretask-interfaces-)
1. [What is Executors framework?](#what-is-executors-framework-)
1. [What is AtomicInteger](#what-is-atomicinteger-)

---

1. ##### Describe synchronization in respect to multi-threading. What is synchronization? [&#10548;](#java-concurrency)

  Several threads access common data.

  In order to keep the data in consistent state the access to it has to be synchronized (i.e. some ordering of data access has to be imposed).

2. ##### Explain different ways of using thread? [&#10548;](#java-concurrency)

  1. Create a long-running computation in a separate thread so the user interface (or whatever other part of the application) is not blocked.
  2. separate out I/O operations which potentially can take a lot of time (e.g. reading from the network) for the same reason
  3. process incoming requests in parallel (usually using thread pool of some size)
  4. Create thread to do some kind of isolated processing, wait for the processing to finish, kill the thread. Create new threads when needed

3. ##### What is the difference between preemptive scheduling and time slicing? [&#10548;](#java-concurrency)

  Not exactly a correct question.

  A scheduler can be preemptive (it's capable to force a process to interrupt its execution and resume it in some time) and non-preemptive (which is unable to interrupt a process and relies on the processes themselves that voluntarily give control to other tasks). Time slicing is a usual technique that is used in a preemptive multitasking system. The scheduler is run every time slice to choose the next process to run (it may happen that it's the same process during few time slices in a row, or it may happen that every time slice a different process is executed )

  To apply these terms to Java world -- replace the "process" with "thread", since the ideas behind scheduling processes in OS are the same as scheduling threads in an application.

4. ##### When a thread is created and started, what is its initial state? [&#10548;](#java-concurrency)

  The thread is then in **"RUNNABLE"** state.

5. ##### Thread vs Runnable, run() vs start() [&#10548;](#java-concurrency)

  See below. The main difference between run() and start() is that the latter creates a separate thread while the former executes the code synchronously

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

7. ##### Synchronization of Java blocks and methods [&#10548;](#java-concurrency)

  Methods declared synchronized and statements contained in synchronized blocks. Only one thread is allowed to be executing instructions inside a synchronized block.

  The main difference between *synchronized block* and *synchronized method* is that you can choose which object will be used for synchronization in case of blocks. The methods are always synchronized with "this"

8. ##### Explain usage of the couple wait()/notify() [&#10548;](#java-concurrency)

  The mechanism is used to allow one thread to signal another. E.g. Consumer signals that he's waiting for the next object to process, or Producer signals that a new object is ready to be processed.

  * wait( ) tells the calling thread to give up the monitor and go to sleep until some other thread enters the same monitor and calls notify( ).
  * notify( ) wakes up the a thread (a random one?) that called wait( ) on the same object.
  * notifyAll( ) wakes up all the threads that called wait( ) on the same object.

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

  ***More details:*** : [javarevisited](http://javarevisited.blogspot.com/2011/06/volatile-keyword-java-example-tutorial.html) (\*) , [dzone](https://dzone.com/articles/java-multi-threading-volatile-variables-happens-be-1)(\*), [mechanical-sympathy](http://mechanical-sympathy.blogspot.fr/2013/02/cpu-cache-flushing-fallacy.html), [jpbempel](http://jpbempel.blogspot.fr/2012/10/volatile.html), [java67](http://java67.blogspot.com/2012/08/what-is-volatile-variable-in-java-when.html)

10. ##### Difference between synchronized and volatile keyword in Java?

  Remember volatile is not a replacement of synchronized keyword but can be used as an alternative in certain cases. Here are few differences between volatile and synchronized keyword in Java.

  1. The volatile keyword in Java is a field modifier while synchronized modifies code blocks and methods.

  2. Synchronized obtains and releases the lock on monitor’s Java volatile keyword doesn't require that.

  3. Threads in Java can be blocked for waiting for any monitor in case of synchronized, that is not the case with the volatile keyword in Java.

  4. Synchronized method affects performance more than a volatile keyword in Java.

  5. Since volatile keyword in Java only synchronizes the value of one variable between Thread memory and "main" memory while synchronized synchronizes the value of all variable between thread memory and "main" memory and locks and releases a monitor to boot. Due to this reason synchronized keyword in Java is likely to have more overhead than volatile.

  6. You can not synchronize on the null object but your volatile variable in Java could be null.

  7. From Java 5 writing into a volatile field has the same memory effect as a monitor release, and reading from a volatile field has the same memory effect as a monitor acquire

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

  The Callable has the method public T call() throws Exception. When an ExecutorService gets submitted a Callable<T> it returns a Future<T>. The get() method on this Future<T> instance has to be called in order to get the result

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

21. ##### What is Executors framework? [&#10548;](#java-concurrency)

  [Oracle_JavaSE](http://docs.oracle.com/javase/tutorial/essential/concurrency/exinter.html)

22. ##### What is AtomicInteger [&#10548;](#java-concurrency)

  AtomicInteger is a class from java.util.concurrent package that provides thread-safe implementation of an Integer.

  More information on AtomicXXX can be found at [Oracle_JavaSE](http://docs.oracle.com/javase/6/docs/api/java/util/concurrent/atomic/package-summary.html)

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
