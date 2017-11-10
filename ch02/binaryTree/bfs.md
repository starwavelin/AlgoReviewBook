# BFS Template

We directly use the binary tree level order traversal as a template for you to understand

### Code
```java
public List<List<Integer>> levelOrder(Node root) {
	List<List<Integer>> res = new ArrayList<>();
	
	if (root == null) {
		return res;
	}

	Queue<Node> queue = new LinkedList<>();
	queue.offer(root);

	while (!queue.isEmpty()) {
		List<Integer> level = new ArrayList<>();
		int size = queue.size();
		for (int i = 0; i < size; i++) {
			Node t = queue.poll();
			if (t.left != null) {
				queue.offer(t.left);
			}
			if (t.right != null) {
				queue.offer(t.right);
			}
			level.add(t.val);
		} 
		res.add(level);
	}
	return res;
}
```

If we don't need to consider levels and just purely bfs traversal of a binary tree. ie. we wanna serialize a binary tree by BFS traversal:
```
/*
Binary Tree:                                                         
    1                                                                        
    / \
  2   3
      / \
    4   5

Queue:

String:
1,2,3,#,#,4,5,#,#,#,#,
*/
```

Then the BFS template can be as simple as:  
```java
public String serialize(TreeNode root) {
	StringBuilder sb = new StringBuilder();

	if (root == null) {
		return null;
	}

	Queue<TreeNode> queue = new LinkedList<>();
	queue.offer(root);
	
	while (!queue.isEmpty()) {
		TreeNode t = queue.poll();
		if (t == null) {
			sb.append("#,");
		} else {
			sb.append(t.val + ",");
			queue.offer(t.left);
			queue.offer(t.right);
		}
	}

	return sb.substring(0, sb.length() - 1);
}
```
