# BFS와 DFS

그래프를 탐색하는 대표적인 두 방법입니다.

## 한눈에 비교

| 구분 | BFS | DFS |
| --- | --- | --- |
| 탐색 방식 | 가까운 정점부터 | 깊게 들어간 뒤 되돌아옴 |
| 대표 자료구조 | 큐(`deque`) | 스택 또는 재귀 |
| 활용 예시 | 가중치 없는 그래프의 최단 경로 | 경로 탐색, 백트래킹 |

## BFS 예제

```python
from collections import deque

graph = {
    "A": ["B", "E"],
    "B": ["A", "D"],
    "C": ["E"],
    "D": ["B", "E"],
    "E": ["A", "C", "D"],
}


def bfs(start):
    queue = deque([start])
    visited = {start}
    order = []

    while queue:
        node = queue.popleft()
        order.append(node)
        for nxt in sorted(graph[node]):
            if nxt not in visited:
                visited.add(nxt)
                queue.append(nxt)

    return order


print(bfs("A"))  # ['A', 'B', 'E', 'D', 'C']
```

## 핵심 정리

- 인접 리스트로 구현한 BFS/DFS의 시간 복잡도는 일반적으로 `O(V + E)`입니다.
- 방문 처리 시점과 인접 정점의 순서에 따라 탐색 순서가 달라질 수 있습니다.
- 방문할 수 있는 정점이 여러 개일 때 **알파벳 순서** 조건이 있다면 탐색 순서를 정렬해서 처리합니다.

!!! tip "코딩테스트 메모"
    BFS에서 큐에 넣는 순간 `visited`에 기록하면 같은 정점을 여러 번 큐에 넣는 일을 방지할 수 있습니다.
