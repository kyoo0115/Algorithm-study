# Dijkstra의 알고리즘 (Dijkstra's Algorithm)

---

## 개요

Dijkstra의 알고리즘은 가중 그래프에서 주어진 출발점과 다른 모든 노드 간의 최단 경로를 찾는 알고리즘입니다. 
이 알고리즘은 경로 탐색, 네트워크 라우팅과 같은 다양한 분야에서 널리 사용됩니다.

## Dijkstra 알고리즘의 작동 원리

Dijkstra 알고리즘은 다음과 같은 주요 단계를 거쳐 작동합니다:

1. **초기화(Initialization)**: 출발 노드의 거리 값을 0으로 설정하고, 다른 모든 노드의 거리 값을 무한대로 설정합니다.
2. **탐색(Exploration)**: 아직 처리되지 않은 노드 중 가장 가까운 노드를 선택합니다.
3. **업데이트(Update)**: 선택한 노드를 통과하여 이동할 때 다른 인접 노드들의 최단 경로를 업데이트합니다.
4. **반복(Repeat)**: 모든 노드가 처리될 때까지 2번과 3번 단계를 반복합니다.

## Dijkstra 알고리즘의 의사 코드

```text
DijkstraAlgorithm(graph, source):
    distance[source] ← 0
    for each vertex v in graph:
        if v ≠ source
            distance[v] ← ∞
            previous[v] ← undefined
        add v to Q

    while Q is not empty:
        u ← vertex in Q with min distance[u]
        remove u from Q

        for each neighbor v of u: 
            alt ← distance[u] + length(u, v)
            if alt < distance[v]:
                distance[v] ← alt
                previous[v] ← u

    return distance[], previous[]
```

## Dijkstra 알고리즘의 적용 분야
- **네트워크 라우팅**: 인터넷 라우팅에서 최적의 경로를 찾는 데 사용됩니다.
- **지도 및 내비게이션**: 최단 경로 찾기, GPS 시스템 등에 활용됩니다.
- **그래프 이론**: 다양한 그래프 문제 해결에 활용됩니다.

## Dijkstra 알고리즘의 장단점
- **장점**: 정확하고 효율적으로 최단 경로를 찾을 수 있습니다. 가중치가 양수인 그래프에서 잘 작동합니다.
- **단점**: 음수 가중치가 있는 그래프에서는 사용할 수 없습니다. 높은 시간 복잡도를 가질 수 있습니다.

## Dijkstra 알고리즘의 시간 복잡도와 공간 복잡도
- **시간 복잡도**: 일반적으로 O(V²)이지만, 우선순위 큐를 사용하면 O(V + E log V)까지 개선됩니다.
- **공간 복잡도**: O(V)입니다.

Dijkstra 알고리즘은 그래프에서 가장 효율적인 경로를 찾는 데 중요한 역할을 합니다.

---