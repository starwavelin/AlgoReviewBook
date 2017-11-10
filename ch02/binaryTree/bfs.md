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