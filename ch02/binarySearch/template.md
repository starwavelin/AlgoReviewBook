# Binary Search Template

The following template with its transformations can be used to find the first, last or any position of a target number in a *Sorted* array.

The following template is for finding the first position the target number occurs in an array, with other options written in the code comments.

```java
public int search(int[] nums, int target) {
	if (nums == null || nums.length == 0) {
		return -1; /* -1 means cannot find target */
	}
	int start = 0, end = nums.length - 1, mid;
	while (start + 1 < end) {
		mid = start + (end - start) / 2; /* avoid overflow */
		if (nums[mid] == target) {
			end = mid; /* You can use start = mid for last position, and return mid for any position */
		} else if (nums[mid] < target) {
			start = mid;
		} else {
			end = mid;
		}
	}

	if (nums[start] == target) {
		return start;
	} else if (nums[end] == target) {
		return end;
	}	/* For last position, you want to flip the checking order to check nums[end] first. For any position, it doesn't matter */

	return -1;
}
```