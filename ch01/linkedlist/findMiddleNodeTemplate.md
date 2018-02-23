# Templates for Finding the Middle Node in Linked List

For a linked list with odd number of nodes, the middle node is the middle one; for a linked list with even nodes, we decide the middle node to be the first one of the middle two nodes.  

Method: Fast slow pointers

### Code
```java
public Node findMiddle(Node head) {
	if (head == null || head.next == null) {
		return head;
	}
	Node fast = head, slow = head;
	while (fast.next != null && fast.next.next != null) {
		fast = fast.next.next;
		slow = slow.next;
	}
	return slow;
}
```