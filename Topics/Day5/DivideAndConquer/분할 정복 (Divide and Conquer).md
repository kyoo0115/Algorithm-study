# 분할 정복 알고리즘 (Divide and Conquer Algorithm)

---

## 개요

분할 정복 알고리즘(Divide and Conquer Algorithm)은 복잡한 문제를 더 작고 관리하기 쉬운 부분 문제로 나누어 해결하는 방식입니다. 이 알고리즘은 문제를 분할하고, 각각의 부분 문제를 독립적으로 해결한 후, 그 해결책을 결합하여 전체 문제의 해답을 도출합니다.

## 분할 정복 알고리즘의 작동 원리

분할 정복 알고리즘은 다음과 같은 세 가지 주요 단계를 거쳐 작동합니다:

1. **분할(Divide)**: 문제를 더 작은 부분 문제로 분할합니다.
2. **정복(Conquer)**: 각 부분 문제를 재귀적으로 해결합니다.
3. **결합(Combine)**: 모든 부분 문제의 해결책을 결합하여 원래 문제의 해답을 얻습니다.

## 분할 정복 알고리즘의 의사 코드

```text
DivideAndConquer(problem):
    if problem is small enough:
        return solve problem directly

    subproblems = divide problem into subproblems
    solutions = []

    for subproblem in subproblems:
        solutions.add(DivideAndConquer(subproblem))

    return combine(solutions)
```

## 분할 정복 알고리즘의 적용 분야
- **정렬 알고리즘**: 퀵 정렬, 병합 정렬 등.
- **수학적 계산**: 거듭 제곱, 행렬 곱셈 등.
- **트리와 그래프 문제**: 이진 탐색 트리, 최소 신장 트리 계산 등.

## 분할 정복 알고리즘의 장단점
- **장점**: 복잡한 문제를 단순화하여 해결할 수 있습니다. 병렬 처리와 효율적인 자원 활용이 가능합니다.
- **단점**: 재귀 호출의 과도한 사용으로 메모리 사용량이 증가할 수 있습니다. 부분 문제들이 서로 중복될 경우 비효율적일 수 있습니다.

## 분할 정복 알고리즘의 시간 복잡도와 공간 복잡도
- **시간 복잡도**: 알고리즘에 따라 다르지만, 일반적으로 O(n log n)인 경우가 많습니다(예: 병합 정렬).
- **공간 복잡도**: 재귀 호출로 인한 스택 사용량에 따라 달라지며, 일반적으로 O(n) 또는 O(log n)입니다.

분할 정복 알고리즘은 재귀적 접근과 효율적인 부분 문제 해결을 통해 복잡한 문제를 간단하게 해결할 수 있게 해줍니다.