Collections
---

List questions:

1. [Draw Collections Framework Class Diagram](#1-draw-collections-framework-class-diagram-)
1. [What is HashMap and Map?](#2-what-is-hashmap-and-map-)
1. [Difference between HashMap and HashTable? Can we make HashMap synchronized?](#3-difference-between-hashmap-and-hashtable-can-we-make-hashmap-synchronized-)
1. [Difference between Vector and ArrayList?](#4-difference-between-vector-and-arraylist-)
1. [What is an Iterator?](#5-what-is-an-iterator-)
1. [List vs Set vs Map. Purposes and definitions](#6-list-vs-set-vs-map-purposes-and-definitions-)
1. [Pros and cons of ArrayList and LinkedList](#7-pros-and-cons-of-arraylist-and-linkedlist-)
1. [TreeSet and LinkedHashSet](#8-treeset-and-linkedhashset-)
1. [What are the advantages of ArrayList over arrays ?](#9-what-are-the-advantages-of-arraylist-over-arrays--)
1. [Principle of storing data in a hashtable](#10-principle-of-storing-data-in-a-hashtable-)
1. [Differences between Hashtable, ConcurrentHashMap and Collections.synchronizedMap()](#11-differences-between-hashtable-concurrenthashmap-and-collectionssynchronizedmap-)
1. [How are hash codes computed?](#12-how-are-hash-codes-computed-)
1. [Is it possible that hash code is not unique?](#13-is-it-possible-that-hash-code-is-not-unique-)
1. [Can we put two elements with equal hash code to one hash map?](#14-can-we-put-two-elements-with-equal-hash-code-to-one-hash-map-)
1. [Iterator and modification of a List. ConcurentModificationException.](#15-iterator-and-modification-of-a-list-concurentmodificationexception-)
1. [What is the significance of ListIterator? What is the difference b/w Iterator and ListIterator?](#16-what-is-the-significance-of-listiterator-what-is-the-difference-bw-iterator-and-listiterator-)
1. [How can we access elements of a collection?](#17-how-can-we-access-elements-of-a-collection-)
1. [What’s the difference between a queue and a stack?](#18-whats-the-difference-between-a-queue-and-a-stack-)
1. [What is the Properties class?](#19-what-is-the-properties-class-)
1. [Which implementation of the List interface provides for the fastest insertion of a new element into the middle of the list?](#20-which-implementation-of-the-list-interface-provides-for-the-fastest-insertion-of-a-new-element-into-the-middle-of-the-list-)
1. [Can you limit the initial capacity of vector in Java?](#21-can-you-limit-the-initial-capacity-of-vector-in-java-)
1. [What method should the key class of Hashmap override?](#22-what-method-should-the-key-class-of-hashmap-override-)
1. [What is the difference between Enumeration and Iterator?](#23-what-is-the-difference-between-enumeration-and-iterator-)
1. [Collections class and Arrays class](#24-collections-class-and-arrays-class-)

---

##### 1. Draw Collections Framework Class Diagram [&#10548;](#collections)

    interface Iterable
    interface Collection extends Iterable
    interfaces List, Queue, Set extend Collection
    interface SortedSet extends Set
    interface Map
    interface SortedMap extends Map
    classes ArrayList, Vector, Stack, LinkedList implement List
    classes HashSet, LinkedHashSet implement Set
    class TreeSet implements SortedSet
    classes HashMap, WeakHashMap, LinkedHashMap implement Map
    class TreeMap implements SortedMap
    utility classes Collections and Arrays

##### 2. What is HashMap and Map? [&#10548;](#collections)

***Map*** -- is a interface. Contains methods to manipulate Key-Value based collections. The main methods of Map interface are put(K,V), get(K), Collection<V> values(), Set<K> keySet(), containsKey(), containsValue()

***HashMap*** -- is one of implementations of the Map interface based on hashcodes of objects used as keys.

##### 3. Difference between HashMap and HashTable? Can we make HashMap synchronized? [&#10548;](#collections)

* Both implement Map interface.
* HashTable is synchronized. It is recommended to use HashMap wherever possible.
* HashTable doesn't allow null keys and values.
* HashMap allows one null key and any number of null values.

We can make it synchronized

```
Map m = Collections.synchronizedMap(new HashMap());
```

##### 4. Difference between Vector and ArrayList? [&#10548;](#collections)

Both implement List interface. ArrayList is not synchronized.

##### 5. What is an Iterator? [&#10548;](#collections)

It is an interface that contains three methods: next(), boolean hasNext(), void remove()

It allows to iterate over the collection

If a class implements iterator then it can be used in foreach loop

##### 6. List vs Set vs Map. Purposes and definitions [&#10548;](#collections)

All three are interfaces.

***List*** -- storing values in specified order.

* Provides methods to get the element by its position: get(i), finding element, ListIterator.
* Known implementations: ArrayList, Vector, LinkedList. List should be used when the order in which the elements are stored matters.

***Set*** -- storing only different objects and at most one null element.

* Known implementations: TreeSet (iterate over the elements in order defined by Comparator, or if the elements implement comparable; provides log(n) performance for basic operations), HashSet -- stores values in buckets defined by their hashcodes. Each bucket is a singly linked list. Provides constant time performance for basic operations. LinkedHashSet

***Map*** -- for storing key-value pairs.

* Map cannot contain duplicate keys.
* Provides three collection views: set of keys, collection of values, set of key-value mappings.
* Know implementations HashMap, EnumMap, TreeMap, LinkedHashMap, WeakHashMap.

##### 7. Pros and cons of ArrayList and LinkedList [&#10548;](#collections)

> ArrayList -- fast random access

> LinkedList -- slow random access. Implement Queue interface. Fast deletion of the element.


* If lots of random reads is anticipated use ArrayList.
* If lots of iterations over the whole list and lots of add/delete -- use LinkedList.

##### 8. TreeSet and LinkedHashSet [&#10548;](#collections)

LinkedHashSet is backed by LinkedHashMap. LinkedHashMap is backed by doubly linked list to enforce ordering on the elements contained in the Map.

If the ordering of the elements in the Set matters to you but you don't want to use a comparator you may use LinkedHashSet since it will enforce ordering in which the elements were added to the set. Otherwise use TreeSet

##### 9. What are the advantages of ArrayList over arrays? [&#10548;](#collections)

1. ArrayList comes with a number of utility methods (e.g. constants, remove, addAll)
2. Type safety
3. Dynamic sizing

On the other hand arrays are a little bit faster and take less memory (packing). Arrays are also able to contain values of primitive types while ArrayList can only contain Objects.

##### 10. Principle of storing data in a hashtable [&#10548;](#collections)

HashSet. add(element) -> element.hashCode() -> mod bucketsCount -> store

HashMap. add(key, value) -> key.hashCode() -> mod bucketsCount -> store(value)

##### 11. Differences between Hashtable, ConcurrentHashMap and Collections.synchronizedMap() [&#10548;](#collections)

ConcurrentHashMap allows concurrent modification of the Map from several threads without the need to block them.

Collections.synchronizedMap(map) creates a blocking Map which will degrade performance, albeit ensure consistency (if used properly).

Use the second option if you need to ensure data consistency, and each thread needs to have an up-to-date view of the map. Use the first if performance is critical, and each thread only inserts data to the map, with reads happening less frequently.

##### 12. How are hash codes computed? [&#10548;](#collections)

If hashCode() method is defined then it is called to calculate the hashcode.

If its not defined the default implementation in Object class does the following:

```
public int hashCode() {
  return VMMemoryManager.getIdentityHashCode(this);
}
```

##### 13. Is it possible that hash code is not unique? [&#10548;](#collections)

It's totally possible. Actually a totally valid hashCode() function could look like this

```
int hashCode(){ return 57; }
```

##### 14. Can we put two elements with equal hash code to one hash map? [&#10548;](#collections)

Yes we can. The hashcode of objects doesn't matter.

Only the hashcode of keys. But even if you want to put keys with the same hashcode it will be ok since it just means that key-value pairs will be put into the same bucket.

##### 15. Iterator and modification of a List. ConcurentModificationException. [&#10548;](#collections)

The iterators returned by this class's iterator method are fail-fast: if the set is modified at any time after the iterator is created, in any way except through the iterator's own remove method, the iterator will throw a ConcurrentModificationException. Thus, in the face of concurrent modification, the iterator fails quickly and cleanly, rather than risking arbitrary, non-deterministic behavior at an undetermined time in the future.

Note that the fail-fast behavior of an iterator cannot be guaranteed as it is, generally speaking, impossible to make any hard guarantees in the presence of unsynchronized concurrent modification. Fail-fast iterators throw ConcurrentModificationException on a best-effort basis. Therefore, it would be wrong to write a program that depended on this exception for its correctness: the fail-fast behavior of iterators should be used only to detect bugs.

##### 16. What is the significance of ListIterator? What is the difference b/w Iterator and ListIterator? [&#10548;](#collections)

* ListIterator allows to perform iteration both ways (first-->last and last-->first)
* From JavaDoc: ListIterator is an iterator for lists that allows the programmer to traverse the list in either direction, modify the list during iteration, and obtain the iterator's current position in the list

##### 17. How can we access elements of a collection? [&#10548;](#collections)

* Depends on the collection type.
* In general: using an iterator, getting by index, getting by key, using iterator on a view

##### 18. What’s the difference between a queue and a stack? [&#10548;](#collections)

In Java Queue is an interface and has a number of implementations. Stack is a class derieved from Vector class.

The Queue interface contains methods to enqueue and dequeue elements: offer(), poll(). Also contains methods to see the first element in the queue: peek(). The queue ordering is not neccessairly FIFO. It can be based on the comparator (PriorityQueue)

The Stack contains methods to add and remove elements to/from a stack. If used correctly enforces LIFO policy. Contains methods push(), pop(), peek(). The problem with Java stack implementation is that it contains all the methods from Vector class which can lead to violation of LIFO policy.

##### 19. What is the Properties class? [&#10548;](#collections)

* Property class is designed to hold properties (i.e. pairs <String, String> -- property name (key) and property value).
* The two main methods of Properties class is getProperty(String name) and setProperty(String name, String value).
* Properties class extends HashTable

##### 20. Which implementation of the List interface provides for the fastest insertion of a new element into the middle of the list? [&#10548;](#collections)

LinkedList. It only requires 4 assignments.
```
Before: ... <--> A <--> B <--> ...
After:  ... <--> A <--> C <--> B <--> ...
```
A changes one reference, B changes one reference, C assigns two references.

##### 21. Can you limit the initial capacity of vector in Java? [&#10548;](#collections)

I'm not sure if limit is correct word to be used in this question.

One can just set the initial capacity of the Vector.

Well you could say that you are putting lower limit on the size of the Vector.

##### 22. What method should the key class of Hashmap override? [&#10548;](#collections)

equals() and hashCode().

##### 23. What is the difference between Enumeration and Iterator? [&#10548;](#collections)

Enumeration is an interface similar to Iterator. But it doesn't have remove() method.

Enumeration acts as Read-only interface, because it has the methods only to traverse and fetch the objects, where as using Iterator we can manipulate the objects also like adding and removing the objects.

##### 24. Collections class and Arrays class [&#10548;](#collections)

The Collections class contains a number of factory methods for creating unmodifiable views or synchronized wrappers of collections, as well as utility methods such as sort, shuffle, reverse

The Arrays class contains a factory method that take an array as input and return a List based on this array (Arrays.asList()). Also contains methods to sort, search, fill and print arrays
