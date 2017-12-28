# 图类型题目的模板

### DFS Template
```java
dfs (node) {
	// process the current node, mark it as visited
	for () {	// traverse all the nodes that are the neighbors of the current node
		标记更改;
		dfs (next sub-circumstance);
		恢复更改;
	}
	return … ;
}
```

### BFS Template
```java
Queue<Type> q = new LinkedList<>();
q.offer(初始状态);
while (!q.isEmpty()) {
	Type t = q.peek(); // OR Type t = q.poll();
	for (    )  {	// 遍历t的各个next状态  next
		//一些操作
		if (next is legal) {
			q.offer(next);
			计数或者维护 etc.
		}
		//一些操作	
	}
}
```