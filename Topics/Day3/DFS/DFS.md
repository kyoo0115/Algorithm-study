# 깊이 우선 탐색 (Depth-First Search, DFS)

---

## 개요

깊이 우선 탐색(Depth-First Search, DFS)은 그래프와 트리 구조에서 널리 사용되는 중요한 탐색 알고리즘입니다. DFS는 한 경로를 끝까지 탐색한 후 다른 경로를 탐색하는 방식으로, "가장 깊은 노드"를 우선적으로 탐색합니다. 이 알고리즘은 미로 찾기, 퍼즐 게임, 네트워크 분석 등 다양한 분야에서 활용됩니다.

## DFS의 작동 원리

DFS는 다음과 같은 단계를 거쳐 작동합니다:

1. <b>스택 초기화</b>: 탐색을 시작할 노드를 스택에 삽입합니다.
2. <b>탐색 실행</b>: 스택이 비어있지 않은 동안 다음을 반복합니다:
    - 스택에서 노드를 하나 꺼냅니다.
    - 해당 노드를 방문 처리합니다.
    - 해당 노드에 인접한 모든 미방문 노드를 스택에 삽입합니다.
3. <b>탐색 종료</b>: 스택이 비어있으면 탐색을 종료합니다.

## DFS의 의사 코드

```text
DFS(graph, startNode):
create a stack S
push startNode to S
mark startNode as visited

    while S is not empty:
        currentNode = pop from S

        for each node N that is adjacent to currentNode:
            if N is not visited:
                push N to S
                mark N as visited
```

- graph: 탐색할 그래프
- startNode: 탐색을 시작할 노드
- S: 탐색 순서를 관리하기 위한 스택
- currentNode: 현재 탐색 중인 노드
- N: currentNode에 인접한 노드

## DFS의 적용 분야
- 퍼즐 게임: 미로 찾기, 퍼즐 해결 등에 사용됩니다.
- 네트워크 분석: 네트워크의 연결성 분석에 사용됩니다.
- 데이터 구조 탐색: 트리나 그래프 구조의 깊이 있는 탐색에 사용됩니다.

## DFS의 장단점
- 장점: 메모리 소비가 BFS보다 적으며, 모든 가능한 경로를 탐색할 수 있습니다.
- 단점: 최단 경로를 보장하지 않으며, 무한 루프에 빠질 위험이 있습니다.

## DFS의 시간 복잡도와 공간 복잡도
- 시간 복잡도: <b>O(V + E)</b> (V: 노드의 수, E: 간선의 수)
- 공간 복잡도: <b>O(V)</b> (V: 노드의 수, 재귀 호출에 의한 추가 공간 포함)