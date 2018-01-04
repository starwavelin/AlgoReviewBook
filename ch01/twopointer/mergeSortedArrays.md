# Templates for Merging Two Sorted Arrays


### Setting a new array of size m+n
```java 
public int[] merge(int[] A, int[] B) { 
	int[] res = new int[A.length + B.length];
	int i = 0, j = 0, k = 0;
	while (i < A.length && j < B.length) {
		res[k++] = (A[i] < B[j]) ? A[i++] : B[j++];
	}
	while (i < A.length) {
		res[k++] = A[i++];
	}
	while (j < B.length) {
		res[k++] = B[j++];
	}
	return res;
}
```
三while loop模板。  
Think: how does the template listed above relate to the merge function defined in merge sort?

