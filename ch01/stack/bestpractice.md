# Best Practice of Wrting Stack in Java

In the past I always used ```Stack``` class from Java API to represent a stack. However, it is not recommended in the industry because ```Stack``` is thread-safe, which will cause overhead. Instead, industry usually uses [```ArrayDeque```](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayDeque.html) to implement a stack.  

### Initialization Old Way
```java 
Stack<T> s = new Stack<>();
```

### Initialization New Way
```java 
Deque<T> stack = new ArrayDeque<>();
```

### Compare of the methods a stack can have  
You should use the methods under ArrayDeque to mimick a stack

| Using Stack| Using ArrayDeque| 
| -----------|:---------------:| 
| push(E e)  | offerLast(E e)  | 
| pop()      | pollLast()      | 
| empty()    | isEmpty()       | 
| peek()     | peekLast()      |

*I personally like to use ```xxxLast()``` methods to mimick push, pop, peek, but you can also use the same set of ```xxxFirst()``` to mimick these actions. But, do please be consistency.* 
