# Merge Sort Sample Code

```
public void mergeSort(int[] nums) {
	sort(nums, 0, nums.length - 1);
}

private void sort(int[] nums, int start, int end) {
	if (end <= start) {	// be careful of this exit condition!!!
		return;
	}
	int mid = start + (end - start) / 2;
	sort(nums, start, mid);
	sort(nums, mid + 1, end);
	merge(nums, start, mid, end);
}

private void merge(int[] nums, int start, int mid, int end) {
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
	for (i = start; i < k; i++) {
		nums[i] = tmp[i];
	}
}
```