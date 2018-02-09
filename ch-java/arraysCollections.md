# Arrays, Array, Collections, Collection

Briefly talk about the difference among "Arrays", "Array", "Collections", "Collection" in Java.  

### Arrays vs Collections
Both of them are Java utility classes, extended from ```java.lang.Object``` class.  
* java.lang.Object
	* java.util.Arrays

* java.lang.Object
	* java.util.Collections

A frequently used method from them are ```Collections.sort()``` or ```Arrays.sort()```

### Collection
Collection is an **interface** in ```java.util``` package. It's the root interface in Collection hierarchy. Many data structure classes implements Collection interface, like LinkedList, HashSet, PriorityQueue, ConcurrentHashMap.  
Collection extends the ```Iterable<E>``` interface, in which we have ```foreach()``` method enabled.

### Array
Array is a final class (cannot be subclasses) extends from the Object class.  
It provides static methods to dynamically create and access Java arrays.
* java.lang.Object
	* java.util.reflect.Array
