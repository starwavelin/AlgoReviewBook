# Divide and Conquer Template

### Code
```java
public ReturnType f(Node root, List<E> res) {
	//Base case: may be like below
	if (root == null) {
		return null;
	}

	//Divide
	ReturnType left = f(root.left);
	ReturnType right = f(root.right);

	//Conquer
	/* Combine the left and right subtree solutions into one */
	/* res will be updated here */
}
```

### Example
One example is [Binary Tree Max Path Sum From Root](binaryTreeMaxPathSumFromRoot.html)

### Further
Divide and Conquer methodology is like MapReduce, where map is "divide" and reduce is "conquer".