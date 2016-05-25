Exceptions
---

List questions:

1. [What are Checked and Unchecked Exception?](#what-are-checked-and-unchecked-exception-)
1. [What are runtime exceptions?](#what-are-runtime-exceptions-)
1. [What is the difference between error and an exception?](#what-is-the-difference-between-error-and-an-exception-)
1. [How to create custom exceptions?](#how-to-create-custom-exceptions-)
1. [If I want an object of my class to be thrown as an exception object, what should I do?](#if-i-want-an-object-of-my-class-to-be-thrown-as-an-exception-object-what-should-i-do-)
1. [If my class already extends from some other class what should I do if I want an instance of my class to be thrown as an exception object?](#if-my-class-already-extends-from-some-other-class-what-should-i-do-if-i-want-an-instance-of-my-class-to-be-thrown-as-an-exception-object-)
1. [How does an exception permeate through the code?](#how-does-an-exception-permeate-through-the-code-)
1. [What are the different ways to handle exceptions?](#what-are-the-different-ways-to-handle-exceptions-)
1. [What is the basic difference between the 2 approaches to exception handling...1> try catch block and 2> specifying the candidate exceptions in the throws clause?](#what-is-the-basic-difference-between-the-2-approaches-to-exception-handling1-try-catch-block-and-2-specifying-the-candidate-exceptions-in-the-throws-clause-)
1. [When should you use which approach?](#when-should-you-use-which-approach-)
1. [Is it necessary that each try block must be followed by a catch block?](#is-it-necessary-that-each-try-block-must-be-followed-by-a-catch-block-)
1. [If I write return at the end of the try block, will the finally block still execute?](#if-i-write-return-at-the-end-of-the-try-block-will-the-finally-block-still-execute-)
1. [If I write System.exit (0); at the end of the try block, will the finally block still execute?](#if-i-write-systemexit-0-at-the-end-of-the-try-block-will-the-finally-block-still-execute-)
1. [How does a try statement determine which catch clause should be used to handle an exception?](#how-does-a-try-statement-determine-which-catch-clause-should-be-used-to-handle-an-exception-)
1. [What is the catch or declare rule for method declarations?](#what-is-the-catch-or-declare-rule-for-method-declarations-)
1. [Pros and cons of using exceptions vs. returning "error value"](#pros-and-cons-of-using-exceptions-vs-returning-error-value-)
1. [Cases when the finally block isn't executed](#cases-when-the-finally-block-isnt-executed-)
1. [What is exception handling mechanism](#what-is-exception-handling-mechanism-)
1. [Bundled exceptions](#bundled-exceptions-)
1. [How to avoid catch block?](#how-to-avoid-catch-block-)
1. [The difference between throw and throws in Java?]()

---
1. ##### What are Checked and Unchecked Exception? [&#10548;](#exceptions)

  * **Checked** --
    * exception that the program has to handle with and to be able to successfully recover from.
    * is checked by the compiler at compile time. It's mandatory for a method to either handle the checked exception or declare them in their throws clause. These are the ones which are a sub class of Exception but doesn't descend from RuntimeException.
  * **Unchecked (Runtime)** --
    * usually signal of a programmatic error. Potentially can happen anywhere.
    * The unchecked exception is the descendant of RuntimeException and not checked by the compiler at compile time.
  * **Error** -- something very bad happened to the JVM or system. Usually cannot be recovered from.

  [detail](http://java67.blogspot.sg/2012/12/difference-between-runtimeexception-and-checked-exception.html)

2. ##### What are runtime exceptions? [&#10548;](#exceptions)

  See above.

3. ##### What is the difference between error and an exception? [&#10548;](#exceptions)

  See above.

4. ##### How to create custom exceptions? [&#10548;](#exceptions)

  Extend from **Exception** class or from **RuntimeException** class.

5. ##### If I want an object of my class to be thrown as an exception object, what should I do? [&#10548;](#exceptions)

  Extend from Exception class (or any of its subclasses)

6. ##### If my class already extends from some other class what should I do if I want an instance of my class to be thrown as an exception object? [&#10548;](#exceptions)

  Nothing. There is no Exception interface.

7. ##### How does an exception permeate through the code? [&#10548;](#exceptions)

  It's either *caught* or it is going to be passed to the next level in call stack.

  If it's *caught* it can be *rethrown* as another Exception which has to be processed in a higher level.

8. ##### What are the different ways to handle exceptions? [&#10548;](#exceptions)

  Declare that the methods throws an exception or catch it.

9. ##### What is the basic difference between the 2 approaches to exception handling...1> try catch block and 2> specifying the candidate exceptions in the throws clause? [&#10548;](#exceptions)

  The main difference is in who is responsible for handling the exception.

10. ##### When should you use which approach? [&#10548;](#exceptions)

  As I understand one should handle the exception if he/she has all the knowledge and resources to do so. And the exception has to be handled as soon as this knowledge is acquired.

  However if you are writing a library you may consider declaring the exceptions that are thrown and force the user of the library to decide how to react to a specific situation. The downside of this approach is that declared exceptions become the part of the API which has to be frozen after being published.

11. ##### Is it necessary that each try block must be followed by a catch block? [&#10548;](#exceptions)

  No. It can be followed by either catch block or finally block or both.

12. ##### If I write return at the end of the try block, will the finally block still execute? [&#10548;](#exceptions)

  Yes it will.

13. ##### If I write System.exit (0); at the end of the try block, will the finally block still execute? [&#10548;](#exceptions)

  No it won't. It also won't execute if the thread where the exception is thrown is terminated.

14. ##### How does a try statement determine which catch clause should be used to handle an exception? [&#10548;](#exceptions)

  The first that has a matching exception type declared.

15. ##### What is the catch or declare rule for method declarations? [&#10548;](#exceptions)

  blah-blah-blah. If you are using a checked exception you either have to catch it or declare that it could be thrown by a method.

16. ##### Pros and cons of using exceptions vs. returning "error value" [&#10548;](#exceptions)

  * Exceptions provide clearer understanding and better code
  * Exceptions can be grouped together to be handled
  * Exceptions can be propagated up in the call stack to be handled where they are supposed to be handled.
  * Exception handling could be slow.
  * In some sense Exceptions are unignorable error codes.

  For example, exceptions are intrusive (eg if they're not handled the program dies).  If you have an error that can be safely ignored, being forced to catch and handle can be painful. However, they're definitely appropriate if the result of quietly ignoring an error is something that will bite you later.

17. ##### Cases when the finally block isn't executed [&#10548;](#exceptions)

  * System.exit() in try or catch block.
  * Error in one of the blocks (e.g. OutOfMemoryError)
  * Thread is terminated, while the whole application still continues.

18. ##### What is exception handling mechanism [&#10548;](#exceptions)

  Blah-blah-blah.

19. ##### Bundled exceptions [&#10548;](#exceptions)

  ```
  IllegalArgumentException
  ConcurrentModificationException
  IllegalStateException
  UnsupportedOperationException
  ArithmeticException
  NullPointerException
  ArrayIndexOutOfBoundsException
  IOException
  ```

20. ##### How to avoid catch block? [&#10548;](#exceptions)

  Declare that method throws the exception. You can still use try/finally.

21. ##### The difference between throw and throws in Java? [&#10548;](#exceptions)

  the throw is used to actually throw an instance of java.lang.Throwable class, which means you can throw both Error and Exception using throw keyword e.g.

  ```
  throw new IllegalArgumentException("size must be multiple of 2")
  ```

  On the other hand, throws is used as part of method declaration and signals which kind of exceptions are thrown by this method so that its caller can handle them. It's mandatory to declare any unhandled checked exception in throws clause in Java.

  [detail](http://javarevisited.blogspot.sg/2012/02/difference-between-throw-and-throws-in.html)
