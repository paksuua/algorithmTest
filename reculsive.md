# 메모이제이션

```python
dic = {0:0, 1:1}

def fibonacci(n):
	if n in dic:
		return dic[n]

	dic[n]=fibonacci(n-1) + fibonacci(n-2)
	return dic[n]
```

# DFS
```
def dfs(graph, v, visited):
  # 현재 노드를 방문 처리
  visited[v] = True
  print(v, end=' ')
  
  # 현재 노드와 연결된 다른 노트를 재귀적으로 방문
  for i in graph[v]:
    if not visited[i]:
      dfs(graph, i, visited)
```


# BFS
```
from collections import deque

# BFS 메소드 정의
def bfs(graph, start, visited):
	queue = deque([start])
	visited[start] = True
	
	while queue:
		v = queue.popleft()
		print(v, end=' ')
		
		for i in graph[v]:
			if not visited[i]:
			queue.append(i)
			visited[i] = True
```

```
# 각 노드가 연결된 정보를 표현 (2차원 리스트)
graph = [
  [],
  [2, 3, 8],
  [1, 7],
  [1, 4, 5],
  [3, 5],
  [3, 4],
  [7],
  [2, 6, 8],
  [1, 7]
]

#  각 노드가 방문된 정보를 표현 (1차원 리스트)
visited = [False] * 9

# 정의된 DFS 함수 호출
dfs(graph, 1, visited)

# 정의된 BFS 함수 호출
bfs(graph, 1, visited)
```







