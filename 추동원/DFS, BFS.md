## 그래프
연결되어있는 원소간의 관계를 표현한 자료구조로 연결한 객체인 __노드__ 와 연결하는 __간선__ 으로 구성된다.

하나의 노드에서 시작하여 간선을 따라 다수의 노드를 방문하는 것을 그래프 탐색이라 한다.

두 노드가 간선으로 연결 된 경우를 두 노드가 인접하다 라고한다. <br><br>

## 그래프 표현 방식
__1. 인접 행렬 방식__ : 2차원 배열에 각 노드가 연결된 형태를 기록하는 방식 (파이썬 = 2차원 리스트)

&nbsp; 첫 행과 첫 열을 각각 시작 노드, 끝 노드로 놓고 각 노드를 연결해주는 간선을 안에다 적어준다. <br>&nbsp; 시작 끝이 자기자신일 경우 0을 넣어주고 연결되는 간선이 없는 경우 무한을 넣어준다 <br>

__2. 인접 리스트 방식__ : 연결리스트 형식으로 그래프 데이터 저장

&nbsp; 2차원 리스트를 만들어주고 바깥쪽 리스트의 인덱스를 노드로 사용하고 안쪽 리스트에 해당 노드가 연결된 노드와 간선의 거리를 넣어준다. <br><br>

## DFS
깊이 우선 탐색으로 그래프에서 깊은 부분을 우선적으로 탐색하는 알고리즘이다.

DFS의 동작 과정은
<br>1. 탐색 시갖 노드를 스택에 삽입하고 방문처리를 한다.
<br>2. 스태의 최상단 노드에 방문하지 않은 인접노드가 있으면 그 인접 노드를 스택에 넣고 방문처리를 한다. 방문하지 않은 인접노드가 없으면 스태에서 최상단 노드를 꺼낸다.
<br>3. 2번의 과정을 더 이상 수행할 수 없을 때까지 반복한다.

<pre><code> 
def dfs(graph, v , visited):
    visited[v] = True
    print(v, end=' ')

    for i in graph[v]:
        if not visited[i]:
            dfs(graph, i, visited)

graph = [
    [],
    [2,3,8],
    [1,7],
    [1,4,5],
    [3,5],
    [3,4],
    [7],
    [2,6,8],
    [1,7]
]

visited = [False]*9
dfs(graph, 1, visited)
</code></pre>
 
## BFS
넓이 우선 탐색으로 시작 노드로 부터 가까운 노드부터 탐색하는 알고리즘이다. dfs와 달리 노드 방문 여부를 반드시 검사해야한다.

BFS의 동작 과정은
<br>1. 탐색 시작 노드를 큐에 삽입하고 방문 처리를 한다.
<br>2. 큐에서 노드를 꺼내 해당 노드의 인접 노드 중에서 방문하지 않은 노드를 모두 큐에 삽입하고 방문 처리를 한다.
<br>3. 2번의 과정을 더 아싱 수행할 수 없을 때까지 반복한다.  

<pre><code>
def bfs(graph, start, visited):
    queue = deque([start])
    visited[start] = True

    while queue:
        v = queue.popleft()
        print(v,end=' ')

        for i in graph[v]:
            if not visited[i]:
                queue.append(i)
                visited[i] = True


graph = [
    [],
    [2,3,8],
    [1,7],
    [1,4,5],
    [3,5],
    [3,4],
    [7],
    [2,6,8],
    [1,7]
]

visited = [False]*9
bfs(graph, 1, visited)

</code></pre>
