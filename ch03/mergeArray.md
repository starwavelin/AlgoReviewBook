# Merge Array Template

This merge array template would be helpful for mergeSort.  
You may also review LeetCode [88. Merge Sorted Array](https://github.com/starwavelin/AlgorithmPractice/blob/master/AlgPrac/src/array/MergeSortedArray.java#L122) as a reference.  

```java
public void merge(int[] nums1, int m, int[] nums2, int n) { /* m - length of nums1; n - length of nums2 */
	int[] tmp = new int[m + n];
	int i = 0, j = 0, k = 0;

	/* 代码块 */
	while (i < m && j < n) {
		tmp[k++] = (nums1[i] < nums2[j]) ? nums1[i++] : nums2[j++];
	}
	while (i < m) {
		tmp[k++] = nums1[i++];
	}
	while (j < n) {
		tmp[k++] = nums2[j++];
	}

	for (i = 0; i < k; i++) {
        nums1[i] = tmp[i];
    }
}
```

The ```merge``` part of mergeSort is to combine the arrays of elements from ```start``` to ```mid``` and from ```mid + 1``` to ```end```  
Surely ```start```, ```mid``` and ```end``` are given from the mergeSort function, which means their values are valid.  
And you can see we will have ```i <= m_index``` and ```j <= n_index``` then.  

```java
public void merge(int[] nums, int start, int mid, int end) {
	int[] tmp = new int[nums.length];
	int i = start, j = mid + 1, k = start;

	while (i <= mid && j <= end) {
		tmp[k++] = (nums[i] < nums[j]) ? nums[i++] : nums[j++];
	}
	while (i <= mid) {
		tmp[k++] = nums[i++];
	}
	while (j <= end) {
		tmp[k++] = nums[j++];
	}

	for (i = start; i < k; i++) { /* when copy to original array nums, i should start from `start` */
		nums[i] = tmp[i];
	}
}
```