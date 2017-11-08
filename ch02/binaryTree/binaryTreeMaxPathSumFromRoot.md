# Binary Tree Max Path Sum From Root

### Problem
Given a binary tree, find the maximum path sum from root. The path may end at any node, and contain at least one node in it.

### Analize
This is the prerequisite questions for LeetCode 124 [Binary Tree Maximum Path Sum](https://leetcode.com/problems/binary-tree-maximum-path-sum/description/) in which the path is defined as any node to any node following the parent-child connection.  
Use Divide and Conquer to solve.  

### Code
```java
public int maxPathSum(TreeNode root) {
	if (root == null) {
		return 0;
	}
	return root.val + Math.max(Math.max(maxPathSum(root.left), maxPathSum(root.right)), 0);
}
```

### Complexity
Time Complexity: O(n) cuz we traversed every node  
Space Complexity: Recursion stack -- O(logn) if balanced tree and O(n) if linear shape tree.