# Selection Sort

### What is Selection Sort?
You can review from [here](http://blog.csdn.net/han_xiaoyang/article/details/12163251) and look for *四、选择排序*  

### 口诀
找最小数，与左互换。  

### Code
```java
public void sort(int[] nums) {
	for (int i = 0; i < nums.length - 1; i++) {
		int minIndex = i;
		for (int j = i + 1; j < nums.length; j++) {
			if (nums[j] < nums[minIndex]) {
				minIndex = j;
			}
		}
		if (minIndex != i) {
			swap(nums, i, minIndex);
		}
	}
}
```

### Notes
Time Complexity:  
Worst: O(n^2)  Average: O(n^2)  Best: O(n^2)  
三者相同的原因：因为无论何种情况每次取min都要扫描余下的数，扫描```(n-1) + (n-2)... + 1 = n(n-1)/2``` 次