OOP and Design Patterns
---
It contains Java Interview questions from SOLID design principles, OOP fundamentals e.g. class, object, interface, Inheritance, Polymorphism, Encapsulation, and Abstraction as well as more advanced concepts like Composition, Aggregation, and Association. It also contains questions from GOF design patterns.

List questions:

1. [What is the difference between an Interface and an Abstract class?](#what-is-the-difference-between-an-interface-and-an-abstract-class-)
1. [What is the different between a constructor and a method?](#what-is-the-different-between-a-constructor-and-a-method-)
1. [State the significance of public, private, protected, default modifiers both singly and in combination and state the effect of package relationships on declared items qualified by these modifiers.](#state-the-significance-of-public-private-protected-default-modifiers-both-singly-and-in-combination-and-state-the-effect-of-package-relationships-on-declared-items-qualified-by-these-modifiers-)
1. [What is an abstract class? How is it different from an interface? Why would you use it?](#what-is-an-abstract-class-how-is-it-different-from-an-interface-why-would-you-use-it-)
1. [Which design pattern have you used in your production code? apart from Singleton?](#which-design-pattern-have-you-used-in-your-production-code-apart-from-singleton-)
1. [Can you explain Liskov Substitution principle?](#can-you-explain-liskov-substitution-principle-)
1. [What is Law of Demeter violation? Why it matters?](#what-is-law-of-demeter-violation-why-it-matters-)
1. [What is Adapter pattern? When to use it?](#what-is-adapter-pattern-when-to-use-it-)
1. [What is "dependency injection" and "inversion of control"? Why would someone use it?](#what-is-dependency-injection-and-inversion-of-control-why-would-someone-use-it-)
1. [Which one is better constructor injection or setter dependency injection?](#which-one-is-better-constructor-injection-or-setter-dependency-injection-)
1. [What is difference between dependency injection and factory design pattern?](#what-is-difference-between-dependency-injection-and-factory-design-pattern-)
1. [Difference between Adapter and Decorator pattern?](#difference-between-adapter-and-decorator-pattern-)
1. [Difference between Adapter and Proxy Pattern?](#difference-between-adapter-and-proxy-pattern-)
1. [What is Template method pattern?](#what-is-template-method-pattern-)
1. [When do you use Visitor design pattern?](#when-do-you-use-visitor-design-pattern-)
1. [When do you use Composite design pattern?](#when-do-you-use-composite-design-pattern-)
1. [The difference between Inheritance and Composition?](#the-difference-between-inheritance-and-composition-)
1. [What is the difference between overloading and overriding](#what-is-the-difference-between-overloading-and-overriding-)
1. [What is meant by Inheritance and what are its advantages?](#what-is-meant-by-inheritance-and-what-are-its-advantages-)
1. [What is the difference between this() and super()?](#what-is-the-difference-between-this-and-super-)
1. [What modifiers may be used with top-level class?](#what-modifiers-may-be-used-with-top-level-class-)
1. [The difference between nested public static class and a top level class in Java?](#the-difference-between-nested-public-static-class-and-a-top-level-class-in-java-)
1. [Difference between Composition, Aggregation and Association in OOP?](#difference-between-composition-aggregation-and-association-in-oop-)
1. [Give me an example of design pattern which is based upon open closed principle?](#give-me-an-example-of-design-pattern-which-is-based-upon-open-closed-principle-)
1. [Difference between Abstract factory and Prototype design pattern?](#difference-between-abstract-factory-and-prototype-design-pattern-)
1. [When do you use Flyweight pattern?](#when-do-you-use-flyweight-pattern-)

---

1. ##### What is the difference between an Interface and an Abstract class? [&#10548;](#oop-and-design-patterns)

  An Interface is a Class with no implementation. You can not create an object from an interface as it has no implementation or fields. (Interface can contain only public static final fields)

  An Abstract Class is another type of Class. It may have some methods which have not been implemented (which will be labeled *abstract*), but it may also have some methods which have been implemented. Abstract Class also can not be used to create an object, as some implementation code will be missing. (Abstract class can contain regular class fields)

  An object can only be instantiated based on a full class (not abstract, not an interface). In Java, a class can implement between *zero or many interfaces*, or it can extend *zero or one abstract or concrete class* only.

  ***When to use abstract class and interface in Java***

  * An abstract class is good if you think you will plan on using inheritance since it provides a common base class implementation to derived classes.
  * An abstract class is also good if you want to be able to declare non-public members. In an interface, all methods must be public.
  * If you think you will need to add methods in the future, then an abstract class is a better choice. Because if you add new method headings to an interface, then all of the classes that already implement that interface will have to be changed to implement the new methods. That can be quite a hassle.
  * Interfaces are a good choice when you think that the API will not change for a while.
  * Interfaces are also good when you want to have something similar to multiple inheritance, since you can implement multiple interfaces.
  * An abstract class is good to define default behavior for a family of class, but the interface is good to define Type which is later used to leverage Polymorphism.

  ***References:*** [programmerinterview](http://www.programmerinterview.com/index.php/java-questions/interface-vs-abstract-class/), [javarevisited](http://javarevisited.blogspot.sg/2013/05/difference-between-abstract-class-vs-interface-java-when-prefer-over-design-oops.html),  [other](https://github.com/snowdream/115-Java-Interview-Questions-and-Answers/blob/master/en/general.md#9-what-is-the-difference-between-an-interface-and-an-abstract-class-)

1. ##### What is the different between a constructor and a method? [&#10548;](##oop-and-design-patterns)

1. ##### State the significance of public, private, protected, default modifiers both singly and in combination and state the effect of package relationships on declared items qualified by these modifiers. [&#10548;](##oop-and-design-patterns)

1. ##### What is an abstract class? How is it different from an interface? Why would you use it? [&#10548;](##oop-and-design-patterns)

    An abstract class is a java class that has one or more abstract methods (no body). Abstract class can not be instantiated. Abstract class defines an interface that has to be implemented by all its subclasses.

    An abstract class is a class which can have state, code and implementation

    [detail](http://java67.blogspot.sg/2014/06/why-abstract-class-is-important-in-java.html)

1. ##### Which design pattern have you used in your production code? apart from Singleton? [&#10548;](#oop-and-design-patterns)

  This is something you can answer from your experience. You can generally say about dependency injection, factory pattern, decorator pattern or observer pattern, whichever you have used. Though be prepared to answer follow-up question based upon the pattern you choose.

1. ##### Can you explain Liskov Substitution principle? [&#10548;](#oop-and-design-patterns)

  This is one of the toughest questions I have asked in Java interviews. Out of 50 candidates, I have almost asked only 5 have managed to answer it. I am not posting an answer to this question as I like you to do some research, practice and spend some time to understand this confusing principle well.

  [detail](http://javarevisited.blogspot.com/2012/03/10-object-oriented-design-principles.html)

1. ##### What is Law of Demeter violation? Why it matters? [&#10548;](#oop-and-design-patterns)

  Believe it or not, Java is all about application programming and structuring code. If you have good knowledge of common coding best practices, patterns and what not to do than only you can write quality code.

  Law of Demeter suggests you "talk to friends and not stranger", hence used to reduce coupling between classes.

  [detail](http://javarevisited.blogspot.com/2014/05/law-of-demeter-example-in-java.html)

1. ##### What is Adapter pattern? When to use it? [&#10548;](#oop-and-design-patterns)

  Another frequently asked Java design pattern questions.

  ***It provides interface conversion.***

  If your client is using some interface but you have something else, you can write an Adapter to bridge them together. This is good for Java software engineer having 2 to 3 years experience because the question is neither difficult nor tricky but requires knowledge of OOP design patterns.

1. ##### What is "dependency injection" and "inversion of control"? Why would someone use it? [&#10548;](#oop-and-design-patterns)

  [detail](http://javarevisited.blogspot.sg/2012/12/inversion-of-control-dependency-injection-design-pattern-spring-example-tutorial.html)

1. ##### Which one is better constructor injection or setter dependency injection? [&#10548;](#oop-and-design-patterns)

  Each has their own advantage and disadvantage.

  Constructor injection guaranteed that class will be initialized with all its dependency, but setter injection provides flexibility to set an optional dependency.

  Setter injection is also more readable if you are using an XML file to describe dependency.

  Rule of thumb is to use constructor injection for mandatory dependency and use setter injection for optional dependency.

  [detail](http://javarevisited.blogspot.sg/2012/11/difference-between-setter-injection-vs-constructor-injection-spring-framework.html)

1. ##### What is difference between dependency injection and factory design pattern? [&#10548;](#oop-and-design-patterns)

  Though both patterns help to take out object creation part from application logic, use of dependency injection results in cleaner code than factory pattern.

  By using dependency injection, your classes are nothing but POJO which only knows about dependency but doesn't care how they are acquired.

  In the case of factory pattern, the class also needs to know about factory to acquire dependency.

  Hence, DI results in more testable classes than factory pattern. Please see the answer for a more detailed discussion on this topic.

  [detail](http://javarevisited.blogspot.sg/2015/06/difference-between-dependency-injection.html)

1. ##### Difference between Adapter and Decorator pattern? [&#10548;](#oop-and-design-patterns)

  Though the structure of Adapter and Decorator pattern is similar, the difference comes on the intent of each pattern.

  The adapter pattern is used to bridge the gap between two interfaces.

  But Decorator pattern is used to add new functionality into the class without the modifying existing code.

  [detail](http://javarevisited.blogspot.sg/2015/01/adapter-vs-decorator-vs-facade-vs-proxy-pattern-java.html)

1. ##### Difference between Adapter and Proxy Pattern? [&#10548;](#oop-and-design-patterns)

  Similar to the previous question, the difference between Adapter and Proxy patterns is in their intent.
  Since both Adapter and Proxy pattern encapsulate the class which actually does the job, hence result in the same structure.

  But Adapter pattern is used for interface conversion while the Proxy pattern is used to add an extra level of indirection to support distribute, controlled or intelligent access.

  [detail](http://javarevisited.blogspot.sg/2015/01/adapter-vs-decorator-vs-facade-vs-proxy-pattern-java.html)

1. ##### What is Template method pattern? [&#10548;](#oop-and-design-patterns)

  Template pattern provides an outline of an algorithm and lets you configure or customize its steps.

  For examples, you can view a sorting algorithm as a template to sort object. It defines steps for sorting but let you configure how to compare them using Comparable or something similar in another language.

  The method which outlines the algorithms is also known as template method.

1. ##### When do you use Visitor design pattern? [&#10548;](#oop-and-design-patterns)

  The visitor pattern is a solution of problem where you need to add operation on a class hierarchy but without touching them.

  This pattern uses double dispatch to add another level of indirection.

1. ##### When do you use Composite design pattern? [&#10548;](#oop-and-design-patterns)

  Composite design pattern arranges objects into tree structures to represent part-whole hierarchies.

  It allows clients treat individual objects and container of objects uniformly.

  Use Composite pattern when you want to represent part-whole hierarchies of objects.

1. ##### The difference between Inheritance and Composition? [&#10548;](#oop-and-design-patterns)

  Though both allows code reuse, Composition is more flexible than Inheritance because it allows you to switch to another implementation at run-time.

  Code written using Composition is also easier to test than code involving inheritance hierarchies.

  [detail](http://javarevisited.blogspot.sg/2015/06/difference-between-inheritance-and-Composition-in-Java-OOP.html)

1. ##### What is the difference between overloading and overriding? [&#10548;](#oop-and-design-patterns)
  ***overloading*** -- adding a method with the same name but different signature
  * Method overloading in Java occurs when two or more methods in the same class have the exact same name but different parameters.
  * Overloading happens at compile time

  ***overriding*** -- changing the method implementation in the subclass
  * An overridden method would have the exact same method name, return type, number of parameters and types of parameters as the method in parent class.
  * The only difference would be the definition of the method.
  * Overriding happens at run time
  * Inheritance is necessary for overriding.

  [detail](http://java67.blogspot.sg/2012/09/difference-between-overloading-vs-overriding-in-java.html)

1. ##### What is meant by Inheritance and what are its advantages? [&#10548;](#oop-and-design-patterns)
  Inheritance is one of principles of OOP. It allows to create class hierarchies.

  Classes can inherit methods and properties from the base classes thus increasing code reuse.

1. ##### What is the difference between this() and super()? [&#10548;](#oop-and-design-patterns)
  * this() calls the constructor of current class.
  * super() calls the superclass constructor
  * super() has to be the first statement of subclass constructor;
  * this and super are references to the current object and to current object treated as superclass.
  * this.new Something() has to be used to create inner classes

1. ##### What modifiers may be used with top-level class? [&#10548;](#oop-and-design-patterns)
  only public or default (package-private)

1. ##### The difference between nested public static class and a top level class in Java? [&#10548;](#oop-and-design-patterns)

  You can have more than one nested public static class inside one class, but you can only have one top-level public class in a Java source file and its name must be same as the name of Java source file.

  [detail](http://javarevisited.blogspot.sg/2012/12/inner-class-and-nested-static-class-in-java-difference.html)

1. ##### Difference between Composition, Aggregation and Association in OOP? [&#10548;](#oop-and-design-patterns)

  If two objects are related to each other, they are said to be associated with each other.

  Composition and Aggregation are two forms of association in object-oriented programming.

  The composition is stronger association than Aggregation.

  In Composition, one object is OWNER of another object while in Aggregation one object is just USER of another object.

  If an object A is composed of object B then B doesn't exist if A ceased to exists, but if object A is just an aggregation of object B then B can exists even if A ceased to exist.

  [detail](http://javarevisited.blogspot.sg/2014/02/ifference-between-association-vs-composition-vs-aggregation.html)

1. ##### Give me an example of design pattern which is based upon open closed principle? [&#10548;](#oop-and-design-patterns)

  This is one of the practical questions I ask experienced Java programmer. I expect them to know about OOP design principles as well as patterns.

  Open closed design principle asserts that your code should be open for extension but closed for modification.

  Which means if you want to add new functionality, you can add it easily using the new code but without touching already tried and tested code.

  There are several design patterns which are based upon open closed design principle e.g. Strategy pattern, if you need a new strategy, just implement the interface and configure, no need to modify core logic.

  One working example is Collections.sort() method which is based on Strategy pattern and follows the open-closed principle, you don't modify sort() method to sort a new object, what you do is just implement Comparator in your own way.

  [detail](http://javarevisited.blogspot.sg/2011/11/great-example-of-open-closed-design.html)

1. ##### Difference between Abstract factory and Prototype design pattern? [&#10548;](#oop-and-design-patterns)

  This is the practice question for you, If you are feeling bored just reading and itching to write something, why not write the answer to this question.

  I would love to see an example the, which should answer where you should use the Abstract factory pattern and where is the Prototype pattern is more suitable.

1. ##### When do you use Flyweight pattern? [&#10548;](#oop-and-design-patterns)

  This is another popular question from the design pattern. Many Java developers with 4 to 6 years of experience know the definition but failed to give any concrete example. Since many of you might not have used this pattern, it's better to look examples from JDK. You are more likely have used them before and they are easy to remember as well. Now let's see the answer.

  Flyweight pattern allows you to share object to support large numbers without actually creating too many objects. In order to use Flyweight pattern, you need to make your object Immutable so that they can be safely shared. String pool and pool of Integer and Long object in JDK are good examples of Flyweight pattern.
