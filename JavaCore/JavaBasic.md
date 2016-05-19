Java Basics
---------------
###1. What is the difference between an Interface and an Abstract class?

An Interface is a Class with no implementation. You can not create an object from an interface as it has no implementation or fields. (Interface can contain only public static final fields)

An Abstract Class is another type of Class. It may have some methods which have not been implemented (which will be labelled *abstract*), but it may also have some methods which have been implemented. Abstract Class also can not be used to create an object, as some implementation code will be missing. (Abstract class can contain regular class fields)

An object can only be instantiated based on a full class (not abstract, not an interface). In Java, a class can implement between *zero or many interfaces*, or it can extend *zero or one abstract or concrete class* only.

***When to use abstract class and interface in Java***

* An abstract class is good if you think you will plan on using inheritance since it provides a common base class implementation to derived classes.
* An abstract class is also good if you want to be able to declare non-public members. In an interface, all methods must be public.
* If you think you will need to add methods in the future, then an abstract class is a better choice. Because if you add new method headings to an interface, then all of the classes that already implement that interface will have to be changed to implement the new methods. That can be quite a hassle.
* Interfaces are a good choice when you think that the API will not change for a while.
* Interfaces are also good when you want to have something similar to multiple inheritance, since you can implement multiple interfaces.

***References:*** [programmerinterview](http://www.programmerinterview.com/index.php/java-questions/interface-vs-abstract-class/), [other](https://github.com/snowdream/115-Java-Interview-Questions-and-Answers/blob/master/en/general.md#9-what-is-the-difference-between-an-interface-and-an-abstract-class-)

###2. What is the purpose of garbage collection in Java, and when is it used?

GC in Java is the mechanism that keeps track of the memory and objects residing in the memory. GC collects the object when it is no longer needed (usually when no references to the object are available).

###3. What is the different between a constructor and a method?

###4. State the significance of public, private, protected, default modifiers both singly and in combination and state the effect of package relationships on declared items qualified by these modifiers.

###5. What is an abstract class?

An abstract class is a java class that has one or more abstract methods (no body). Abstract class can not be instantiated. Abstract class defines an interface that has to be implemented by all its subclasses.

###6. What is static in java?

*static* is java language keyword.

1. When used with a method defines a method of a class.
2. When used with a field defines a class field.
3. When used on an nested class declaration defines a static nested class.
4. Can be used as a static initialization block.

###7. What is final?

###8. What is overriding?

###9. What are different type of inner classes?

* nested class
* inner class
* local class
* anonymous

###10. Can a top level class be private or protected?

No, it is only allowed to be public or have to default access modifier.

###11. What is the different between declaring a variable and defining a variable?

###12. What type of parameter passing does Java support?

Java passed all parameters by values. The references to objects are passed by values.

###13. Give a simplest way to find out the time a method takes for execution without using any profiling tool?
System.currentTimeMillis() in the beginning and end of the method

###14. Is Empty .java file a valid source file?

Yes it is.

###15. Can a .java file contain more than one java classes?

Yes it can. It has to contain only one top level public java class but it can contain any number of inner, anonymous and top level classes with default access modifier.

###16. Is String a primitive data type in Java?

No. String is an Object. An immutable one.

###17. What happens if you dont initialize an instance variable of any of the primitive types in Java?

It gets assigned the default value. 0 for int and long, 0.0 for float and double, false for boolean. Though I tried to compile a class where variables were not initialized and it didn't compile.

###18. What are the different scopes for Java variables?

static fields, instance fields, method parameters, local variables

###19. What is the default value of the local variables?

No default value. Default values are assigned to instance fields. Local variables have to be explicitly initialized.

###20. Does garbage collection guarantee that a program will not run out of memory?

No.

###21. What is the purpose of finalization?

Free up the resources. (e.g. close connections and streams, release a lock etc)

###22. Can a public class MyClass be defined in a source file named YourClass.java?

No. Unless it is a nested class public class.

###23. What will be the output of the following statement? System.out.println ("1" **+ 3);

13

###24. What will be the default values of all the elements of an array defined as an instance variable?

All elements will be initialized to default value of corresponding type.

###25. Length in bytes for primitive types

| Primitive type| length in bytes  | Comment                                 |
| :------------ |:----------------:| ---------------------------------------:|
| boolean       | 1 bit            |  saved as 4 bytes; 1 byte in an array   |
| char          | 2 bytes          |  unsigned                               |
| byte          | 1 byte           |                                         |
| short         | 2 bytes          |                                         |
| int           | 4 bytes          |                                         |
| long          | 8 bytes          |                                         |
| float         | 4 bytes          |                                         |
| double        | 8 bytes          |                                         |

###26. Contract between equals() and hashCode()

if a.equals(b) returns true then a.hashCode() == b.hashCode() is also true. Note that equal hashCode doesn't mean anything.

###27. What different between StringBuffer and StringBuilder?

StringBuilder -- new. StringBuffer -- old. StringBuffer -- synchronized. Where possible use StringBuilder.
Both represent mutable sequence of characters.

###28. What internal methods of String do you know?

static methods of String class: valueOf, indexOf, lastIndexOf, replace, contains, startsWith, endsWith, substring, matches, split, equals, isEmpty

###29. Purpose, types, and creation of nested classes?

###30. What does it mean that an object or a class is mutable or immutable?

Immutability: the state of the object doesn't change

###31. Is it enough to define this class as final? To make this class immutable?

No. If the class is declared final it only means that it cannot be subclassed. 

If the instance of the class is declared to be final it only means that the reference will not change. 

The inner state of the object in both cases can change.

###32. Besides “String” do you know any other immutable classes?

###33. Increasing/decreasing of methods visibility (inheritance)**

The main rule is that visibility cannot be reduced in the subclass

***References:*** [stackoverflow](http://stackoverflow.com/questions/6851612/java-access-modifiers-and-overriding-methods)

###34. You need to create the string, which contains 1,000,000 random numbers, comma separated. How would you do that, considering performance?

I would use StringBuilder class

###35. Garbage collection principle?

The garbage collector first performs a task called marking. The garbage collector traverses the application graph, starting with the root objects; those are objects that are represented by all active stack frames and all the static variables loaded into the system.

Each object the garbage collector meets is marked as being used, and will not be deleted in the sweeping stage. The sweeping stage is where the deletion of objects take place.

###36. How is the virtual space divided in Java?

 [stackoverflow](http://stackoverflow.com/questions/1262328/how-is-the-java-memory-pool-divided)
 
 [oracle_java6](http://docs.oracle.com/javase/6/docs/technotes/guides/management/jconsole.html)
 
###37. What difference between float and BigDecimal. How they store the data?

float is floating point number and can loose precision during the computations.

BigDeciamal is fixed point number. The computations (which type of computations?) are guaranteed to maintain the needed precision.

Internally BigDecimal consists of an arbitrary precision integer unscaled value and a 32-bit integer scale

If no rounding mode is specified and the exact result cannot be represented, an exception is thrown

###38. What is deep copy of Java object?

Deep copy creates a copy of the object including deep copies of all its fields.

###39. How and in what cases we need to configure size of memory areas in Java?

In case of getting OutOfMemoryError: Java heap space. What other cases?

JVM parameter -Xmx###m where ### is number of megabytes you need for the JVM.

-Xms###m to set the initial heap size

More info on this topic can be found here: <http://blog.codecentric.de/en/2011/03/java-memory-configuration-and-monitoring-3rd-act/>

###40. What is an Object and how do you allocate memory to it?

###41. What are methods and how are they defined?

###42. What is casting?

changing the type of the object.


###43. What is the difference between an argument and a parameter?

parameter -- abstract. argument -- concrete value of the parameter.

parameters of the function are defined when the function is declared.

arguments of the function are defined when it is called.

###44. What is final, finalize() and finally?

final -- Java keyword

finalize() -- gets called before the object is GC-ed

finally -- Java keyword used in exception handling

###45. What is UNICODE?

See info on Unicode here http://docs.oracle.com/javase/1.5.0/docs/api/java/lang/Character.html

###46. What are Transient and Volatile Modifiers?

Transient signifies that the field is not part of the object state (e.g. it's some derieved value or some cache). Transient fields are not present in serialized representation of the object.

If field is declared with volatile keyword then any thread that reads the field will see the most recently written value [Effective Java Item 66]

###47. What is the difference between overloading and overriding?

***overloading*** -- adding a method with the same name but different signature

* Method overloading in Java occurs when two or more methods in the same class have the exact same name but different parameters.
* Overloading happens at compile time

***overriding*** -- changing the method implementation in the subclass

* An overridden method would have the exact same method name, return type, number of parameters and types of parameters as the method in parent class.
* The only difference would be the defination of the method.

###48. What is meant by Inheritance and what are its advantages?

Inheritance is one of principles of OOP. It allows to create class hierarchies. 

Classes can inherit methods and properties from the base classes thus increasing code reuse.

###49. What is the difference between this() and super()?

* this() calls the constructor of current class.
* super() calls the superclass constructor
* super() has to be the first statement of subclass constructor;
* this and super are references to the current object and to current object treated as superclass.
* this.new Something() has to be used to create inner classes

###50. What modifiers may be used with top-level class?

only public or default (package-private)

###51. What is a package?

In Java package is a mechanism to oragnize classes into modules.

###52. What is the difference between Integer and int?

Integer is a wrapper class for int primitive type. 

Integer can be used in generic collections whereas int cannot.

Also contains a number of utility methods.

###53. What is a cloneable interface and how many methods does it contain?

Cloneable -- is a marker interface and it doesn't contain any methods. 

It determines the behavior of Object’s protected clone implementation: if a class implements Cloneable, Object’s clone method returns a field-by-field copy of the object; otherwise it throws CloneNotSupportedException

###54. Can you have an inner class inside a method and what variables can you access?

You can create a local or anonymous class inside the method. It can access only final variables.

###55. What is the difference between static and non-static variables?

a) The way they are initialized. Static are initalized when the class is loaded. Non-static -- when it's instantiated.

b) Non-static belong to the instance of an object while static are class variables.

c) Static are accessed using ClassName.varName

###56. How does Java handle integer overflows and underflows?

Main Method
---

###1. Can an application have multi classes having main method?

Yes, it can. But only one main method can be used as entrance point for the program.

###2. Can I have multiple main methods in the same class?

No, if you mean `public static void main(String[] args)`.
Yes, if you mean a method with a name "main" and any other signatures.

###3. What if the main method is declared as private?

The class will compile but the method cannot be used as an entrance point.

###4. What if the static modifier is removed from the signature of the main method?

It become an instance method. No longer an entrance point but just a valid regular method.

###5. What if I do not provide the String array as the argument to the method?

You just define a static method called "main" with no parameters. It cannot be used as entrance point.

###6. What is the first argument of the String array in main method?

These are the parameters passed to the program from command line.

###7. If I do not provide any arguments on the command line, then the String array of Main method will be empty or null?

Array of size 0

###8. Can main method be declared final?
Yes it can be declared as final

Reference
---
[svozniuk-repo](https://raw.githubusercontent.com/svozniuk/java-interviews/master/Java%20Core/Java%20Basics.md)