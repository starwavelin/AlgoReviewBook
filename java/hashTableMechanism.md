# The Machenism of HashMap in Java

In the context of algorithm discussion, we can use the term *HashTable* to discuss the data structure of doing map with key and value pairs. Then, in a specific language like Java, this term has at least 3 representatives: **HashSet**, **HashMap** and **HashTable**.

In this document we particularly focus on the machenism of **HashMap** in Java.

#### Interview Questions
1. Hash: 1-1, 1-many, many-1, many-many, which?  
ideal: 1-1; many-1 is fair enough.  
2. Search time complexity?  
O(1). 是因用了hashcode做索引，来降低搜索时间。
3. What is rehashing?  
Rehashing是指在哈希表被充满的情况下，我们double那个array的size，使得所有元素
足够放入新的underground array with arrayIndex = hashcode % updatedArraySize;的过程。
4. HashMap growth rate?  
2x
5. How to resolve conflicts in Java HashMap?  
Separate chaining, with newer element inserted to the head of the list.
6. What's iteration order of HashMap?  
遍历一般的HashMap其顺序不定，一般与元素插入的顺序不同。

### What is Hash?
The process of converting an object into a number (hash code).  
Two identical objects will have the same hash code.

### What is HashCode？
1. How to design hashCode (Mathematics problem, not the key point in this doc)  
But here are hashCode() 函数设计三原则：1. generating the same code for repeated calling in the
same application; 2. equal objects should have the identical hashcode; 3.
Idential hashcode does Not mean its corresponding objects are the same, but good
to have (corresponding objects to be same).  
2. How to form the same key of a HashMap
(or say: same index of the underground array)  
Relate to the LC Problem: Group Anagrams.

### HashTable (Data Structure)
比喻：  
hash过程或者说hashCode()函数作用：一个汉字 到 拼音  
HashMap的Mapping机制：拼音 到 对应字典的哪一页  

即：hashcode相当于拼音，arrayIndex相当于字典中的页。  
```
arrayIndex = hashCode % arrayLength;
```

Linear Probing解决Collision的办法容易导致的问题 Clustering (元素堆积)

### HashMap in Java


#### HashSet


#### LinkedHashMap
LinkedList + HashMap   
LInkedList maintains the entries in their insertion order  
Then, traversing LinkedHashMap preserves the entry insertion order

### Q and A

#### Q1: Why does HashMap easily get dead-locked in high concurrency circumstances?
Answer: [HashMap 死锁分析](http://blog.csdn.net/lantian0802/article/details/42487803)  
Core Source Code  

#### Q2: What is the optimization on HashMap in Java 8?
Answer: 1. Convert the linkedlist into a BST.
