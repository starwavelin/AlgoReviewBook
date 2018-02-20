# Templates for Reverse Linked List


### Iterative Way
```java 
public Node reverse(Node head) {
	Node prev = null, next = null;
	while (head != null) {
		next = head.next;
		head.next = prev;
		prev = head;
		head = next;
	}
	return prev;
}
```