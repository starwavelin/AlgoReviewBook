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

### Matrix Movement Template
Assume you have a matrix of numbers representing the graph, and from each cell, you can either move up, down, left or right, in total 4 directions.  
ie. [200. Nunber of Islands](https://leetcode.com/problems/number-of-islands/description/)  
Then, assume x represents the row, and y represents the column. So we have *x-1* represents move up 1 cell and *y+1* represents move right 1 cell. Then,
```java
/* row, col are the original coordinates passed in from the parameters */
int[] dx = new int[]{-1, 1, 0, 0};
int[] dy = new int[]{0, 0, -1, 1};
for (int i = 0; i < 4; i++) { //cuz 4 directions
	int rowNum = row + dx[i];
	int colNum = col + dy[i];
	//dfs(grid, rowNum, colNum, m, n); //m - num of rows; n - num of columns.
}
```

