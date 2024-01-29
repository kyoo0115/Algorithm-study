# 플로이드-워셜 알고리즘 (Floyd-Warshall Algorithm)

---

## 개요

플로이드-워셜 알고리즘은 모든 쌍 최단 경로 문제를 해결하는 알고리즘입니다. 
이 알고리즘은 그래프 내의 모든 정점 쌍 사이의 최단 경로를 찾습니다. 
가중치가 있는 그래프(양수 또는 음수)에서 사용할 수 있으며, 음의 가중치 순환을 감지할 수도 있습니다.

## 플로이드-워셜 알고리즘의 작동 원리

플로이드-워셜 알고리즘은 다음과 같은 주요 단계를 거쳐 작동합니다:

1. **초기화(Initialization)**: 그래프의 인접 행렬을 이용하여 각 노드 쌍의 최단 거리를 초기화합니다.
2. **경로 갱신(Path Update)**: 모든 정점을 중간 경유지로 하여 두 노드 사이의 최단 경로를 갱신합니다.
3. **반복(Iteration)**: 모든 정점 쌍에 대해 이 과정을 반복하여 최단 경로를 찾습니다.

## 플로이드-워셜 알고리즘의 의사 코드

```text
FloydWarshallAlgorithm(graph):
    let distance be a |V|×|V| array of minimum distances initialized to ∞ (infinity)
    for each vertex v:
        distance[v][v] ← 0
    for each edge (u, v):
        distance[u][v] ← weight(u, v)

    for k from 1 to |V|:
        for i from 1 to |V|:
            for j from 1 to |V|:
                if distance[i][k] + distance[k][j] < distance[i][j]:
                    distance[i][j] ← distance[i][k] + distance[k][j]

    return distance
```

## 플로이드-워셜 알고리즘의 적용 분야
- **경로 계획 및 네트워크 분석**: 다중 출발점 및 도착점을 가진 경로 계획에 사용됩니다.
- **그래프 이론**: 그래프 내의 최단 경로 문제 해결에 널리 사용됩니다.

## 플로이드-워셜 알고리즘의 장단점
- **장점**: 모든 쌍 최단 경로를 단순하고 효율적으로 찾을 수 있습니다. 음의 가중치가 있어도 사용할 수 있습니다.
- **단점**: 시간 및 공간 복잡도가 높으며, 매우 큰 그래프에는 적합하지 않을 수 있습니다.

## 플로이드-워셜 알고리즘의 시간 복잡도와 공간 복잡도
- **시간 복잡도**: O(V³), 여기서 V는 정점의 수입니다.
- **공간 복잡도**: O(V²), 최단 경로 거리를 저장하기 위한 2차원 배열이 필요합니다.

플로이드-워셜 알고리즘은 그래프의 모든 정점 쌍 간의 최단 경로를 찾는 데 효과적인 방법을 제공합니다.
