# 너비 우선 탐색 (Breadth-First Search, BFS)

---

## 개요

너비 우선 탐색(Breadth-First Search, BFS)은 그래프와 트리 구조에서 사용되는 중요한 탐색 알고리즘입니다. 
이 방법은 "가장 가까운 노드"부터 탐색을 시작하여 점차 멀리 떨어진 노드로 이동하는 방식으로 작동합니다. 
BFS는 주로 최단 경로 문제를 해결하거나, 레벨 별 탐색이 필요한 경우에 사용됩니다.

## BFS의 작동 원리

BFS는 다음과 같은 단계를 거쳐 작동합니다:

1. <b>큐 초기화</b>: 탐색을 시작할 노드를 큐에 삽입합니다.
2. <b>탐색 실행</b>: 큐가 비어있지 않은 동안 다음을 반복합니다:
   - 큐에서 노드를 하나 꺼냅니다.
   - 해당 노드를 방문 처리합니다.
   - 해당 노드에 인접한 모든 미방문 노드를 큐에 삽입합니다.
3. <b>탐색 종료</b>: 큐가 비어있으면 탐색을 종료합니다.

## BFS의 의사 코드

```text
BFS(graph, startNode):
create a queue Q
enqueue startNode to Q
mark startNode as visited

    while Q is not empty:
        currentNode = dequeue from Q

        for each node N that is adjacent to currentNode:
            if N is not visited:
                enqueue N to Q
                mark N as visited
```

- graph: 탐색할 그래프
- startNode: 탐색을 시작할 노드
- Q: 탐색 순서를 관리하기 위한 큐
- currentNode: 현재 탐색 중인 노드
- N: currentNode에 인접한 노드

## BFS의 적용 분야
- 소셜 네트워크: 친구의 친구 찾기, 최단 연결 경로 탐색 등에 사용됩니다.
- 경로 찾기: 미로 찾기, 최단 경로 찾기 등에 사용됩니다.
- 네트워크 브로드캐스팅: 네트워크 시스템에서 데이터를 효율적으로 전파하는 데 사용됩니다.

## BFS의 장단점
- 장점: 최단 경로를 보장하며, 구현이 비교적 단순합니다.
- 단점: 큰 그래프에서는 메모리 소비가 크고, 모든 노드를 방문해야 하므로 시간이 오래 걸릴 수 있습니다.

## BFS의 시간 복잡도와 공간 복잡도
- 시간 복잡도: <b>O(V + E)</b> (V: 노드의 수, E: 간선의 수)
- 공간 복잡도: <b>O(V)</b> (V: 노드의 수)