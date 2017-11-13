# Bubble Sort

### What is Bubble Sort?
You can review from [here](http://blog.csdn.net/han_xiaoyang/article/details/12163251) and look for *五、冒泡排序*  

### 口诀
两两比较，大数逐步浮动到后面。  

### Code
```java
public void sort(int[] nums) {
	for (int i = nums.length - 1; i > 0; i--) {
		for (int j = 1; j <= i; j++) { /* 大数逐渐移动到后面，所以是从nums.length-1 -- 0 逐步有序化*/
			if (nums[j] < nums[j-1]) {
				int t = nums[j];
				nums[j] = nums[j-1];
				nums[j-1] = t;
			}
		}
	}
}
```

### 备注
Because Bubble Sort always requires O(n^2) swaps among the n numbers, modern textbook usually uses Insertion Sort as a good example of simple sorts, given that Insertion Sort only requires O(n) swaps.
