# Tips of using HashTable in Java

### Definition of HashTable
The definition of HashTable in this context is general; it is not about the thread-safe *HashTable* class in Java, but about *HashMap*, *HashSet*, etc.

### HashMap Traverse
按key traverse 更高效
```java
Map<Integer, List<List<Integer>>> twoSumMap = new HashMap<>();
for (Integer key : twoSumMap.keySet()) {...}
```

### HashMap is primitive type unfriendly
所以，下面这样写是会 **compile error: unexpected type**
```
Map<Integer, Integer> indegrees = new HashMap<>();
indegrees.getOrDefault(pair[0], 0)++; 
/* ++是无法直接把对这个primitive value进行运算后的结果赋给它自己的; 核心即在于 x.foo() 得到的是一个返回值，我们不能对返回值进行++操作，只能对一个变量进行这样的操作 */
```
但下面这样用put的写法就可以了：
```indegrees.put(pair[0], indegrees.getOrDefault(pair[0], 0) + 1);```
另外，以下写法有效果吗？
```graph.getOrDefault(pair[1], new ArrayList<>()).add(pair[0]);```
答案是无效果。因为尽管key *pair[1]* 的对应值某某List加上了一个元素，但这个加上后的结果并没有赋给 *pair[1]* 所对应的在Map中的<K,V>所以是无效的。
而且经测试 ```System.out.println(graph.getOrDefault(pair[1], new ArrayList<>()).add(pair[0]));```打印出来的是true. 想想这是为什么？ 原因就在于List中的add方法return的结果。想要有效，建议在这种value为object type的情况下不用getOrDefault写法，我们可以写为：
```java
if (graph.containsKey(pair[1])) {
    graph.get(pair[1]).add(pair[0]);    
} else {
    List<Integer> latters = new ArrayList<>();
    latters.add(pair[0]);
    graph.put(pair[1], latters);
}
```


