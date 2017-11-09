# DFS Template

The binary tree's DFS template is basically about the 3 type of traverse: preorder, inorder and postorder.  

The following code use pre-order traversal as an example:  

```java
public void traverse(Node root) {
	if (root == null) {
		return;
	}

	//Do something with root

	traverse(root.left);
	traverse(root.right);
}
```