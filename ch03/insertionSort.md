# Insertion Sort

### What is Insertion Sort?
The first couple (worst case scenario only the first one) elements are already sorted, and we just find the next unsorted element, and find the right posiition for this element to be added in, and shift the elements that come after this element being inserted.  
You can review from [here](http://blog.csdn.net/han_xiaoyang/article/details/12163251) and look for *一、插入排序*  

### 口诀
局部有序，挪移插入。

### Code
```java
public void sort(int[] nums) {
	for (int i = 1; i < nums.length; i++) { /* starting from i=1 cuz i=0 is definitely sorted */
		int j = i; 
		int cur = nums[j];
		while (j > 0 && cur < nums[j-1]) { //挪移
			nums[j] = nums[j-1];
			j--;
		}
		nums[j] = cur; //插入
	}
}
```
注意：  
1. 双指针法：移动着的j来实现挪移和插入  
2. 要先把```nums[j]```用变量存起来，否则在挪移中，```nums[j]```被更新而没有事先存，就丧失了要插入的小的数

### Notes
Time Complexity:  
Worst: O(n^2)   
Best: O(n) comparions and O(1) swap.
Best case O(n) will occur if the given numbers are already sorted in ascending order, then we only loop the nums and no insertions involved; or there is just one element needs to be inserted into front.    
That said, Insertion Sort will be efficient if the given numbers are pretty much ordered.  