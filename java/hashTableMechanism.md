# The Machenism of HashMap in Java

In the context of algorithm discussion, we can use the term *HashTable* to discuss the data structure of doing map with key and value pairs. Then, in a specific language like Java, this term has at least 3 representatives: **HashSet**, **HashMap** and **HashTable**.

In this document we particularly focus on the machenism of **HashMap** in Java.

### Waht is Hash?


### What is HashCode？

1. How to design hashcode (Mathematics problem, not the key point in this doc)  
2. How to get a hashcode  
Relate to Group Anagram.


### HashTable (Data Structure)


### HashMap in Java


#### HashSet


#### LinkedHashMap



### Q and A

#### Q1: Why does HashMap easily get dead-locked in high concurrency circumstances?
Answer: [HashMap 死锁分析](http://blog.csdn.net/lantian0802/article/details/42487803)  
Core Source Code  

#### Q2: What is the optimization on HashMap in Java 8?
Answer: 1. Convert the linkedlist into a BST.