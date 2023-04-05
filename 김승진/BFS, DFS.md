# BFS - 너비 우선 탐색
- 그래프의 깊은 부분을 우선적으로 탐색하는 알고리즘이다.
- 주로 Queue와 while문을 활용한다는 특징이 있다.

## 예시 코드
```
dr = ((0, 1), (0 ,-1), (1, 0), (-1 ,0))
board = [[]]
visited = [[]]

def bfs():
    q = deque()
    q.append(())
    while q:
        x, y = q.popleft()
        for dx, dy in dr:
            nx = x + dx
            ny = y + dy
            if 0 < nx < n and 0 <= ny < y and not visited[nx][ny]:
                visited[nx][ny] = True
                q.append(())
```

# DFS - 깊이 우선 탐색
- 가까운 노드부터 탐색하는 알고리즘 이다.
- 주로 재귀함수를 통해 구현한다는 특징이 있다.

## 예시 코드
```
def dfs(board, v, visited):
    visited[v] = True
    for i in graph[v]:
        if not visited[i]:
            dfs(board, i, visited)
```
