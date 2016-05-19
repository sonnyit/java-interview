Collections
---

### 1. Draw Collections Framework Class Diagram

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

###2. What is HashMap and Map?

***Map*** -- is a interface. Contains methods to manipulate Key-Value based collections. The main methods of Map interface are put(K,V), get(K), Collection<V> values(), Set<K> keySet(), containsKey(), containsValue()

***HashMap*** -- is one of implementations of the Map interface based on hashcodes of objects used as keys.

###3. Difference between HashMap and HashTable? Can we make HashMap synchronized?

Both implement Map interface. HashTable is synchronized. It is recommended to use HashMap wherever possible. HashTable doesn't allow null keys and values. HashMap allows one null key and any number of null values.

We can make it synchronized

	Map m = Collections.synchronizedMap(new HashMap());

###4. Difference between Vector and ArrayList?

Both implement List interface. ArrayList is not synchronized.

###5. What is an Iterator?

It is an interface that contains three methods: next(), boolean hasNext(), void remove()

It allows to iterate over the collection

If a class implements iterator then it can be used in foreach loop

###6. List vs Set vs Map. Purposes and definitions

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

###7. Pros and cons of ArrayList and LinkedList

ArrayList -- fast random access

LinkedList -- slow random access. Implement Queue interface. Fast deletion of the element.

If lots of random reads is anticipated use ArrayList.

If lots of iterations over the whole list and lots of add/delete -- use LinkedList.

###8. TreeSet and LinkedHashSet

LinkedHashSet is backed by LinkedHashMap. LinkedHashMap is backed by doubly linked list to enforce ordering on the elements contained in the Map.

If the ordering of the elements in the Set matters to you but you don't want to use a comparator you may use LinkedHashSet since it will enforce ordering in which the elements were added to the set. Otherwise use TreeSet
