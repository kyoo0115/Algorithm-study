# 동적 프로그래밍 (Dynamic Programming)

---

## 개요

동적 프로그래밍 (Dynamic Programming, DP)은 복잡한 문제를 여러 개의 작은 하위 문제로 나누어 해결하는 알고리즘 설계 기법입니다. 각 하위 문제는 한 번만 계산되며, 계산 결과는 재활용됩니다. 이 방법은 중복 계산을 피해 계산 효율성을 높입니다. 주로 최적화 문제, 검색 문제 등에 사용됩니다.

## 동적 프로그래밍의 작동 원리

동적 프로그래밍은 다음과 같은 주요 단계를 거쳐 작동합니다:

1. **문제 분할**: 큰 문제를 작은 하위 문제로 나눕니다.
2. **하위 문제 해결**: 각 하위 문제를 독립적으로 해결하고, 그 결과를 저장합니다.
3. **결과 재활용**: 하위 문제의 해결 결과를 재활용하여 큰 문제의 해답을 구합니다.
4. **최종 해답 도출**: 모든 하위 문제의 해결 결과를 통합하여 최종 해답을 도출합니다.

## 동적 프로그래밍의 의사 코드

```text
DynamicProgramming(problem):
    문제의 하위 문제로 분할합니다.
    하위 문제의 초기 해답을 정의합니다.

    for 각 하위 문제에 대해:
        하위 문제의 해답을 계산합니다.
        계산된 해답을 저장합니다.

    전체 문제의 해답을 구성합니다.
    최종 해답을 반환합니다.
```

## 동적 프로그래밍의 적용 분야

- **최적화 문제**: 배낭 문제, 최장 공통 부분 수열, 최단 경로 문제 등의 최적화 문제를 해결합니다.
- **검색 문제**: 특정 조건을 만족하는 요소를 찾는 문제에 사용됩니다.
- **수치 해석**: 피보나치 수열, 이항 계수 계산 등 수치 해석 문제에 활용됩니다.

## 동적 프로그래밍의 장단점

- **장점**: 중복 계산을 방지하여 효율성을 높이고, 복잡한 문제를 단순화하여 해결 가능합니다.
- **단점**: 모든 하위 문제의 해결 결과를 저장해야 하기 때문에 메모리 사용량이 많을 수 있습니다. 또한, 적절한 하위 문제로의 분할이 어려울 수 있습니다.

## 시간 복잡도와 공간 복잡도

- **시간 복잡도**: 문제에 따라 다르며, 일반적으로 하위 문제의 수와 각 하위 문제를 해결하는 데 필요한 시간에 의해 결정됩니다.
- **공간 복잡도**: 하위 문제의 해결 결과를 저장하기 위한 공간이 필요하므로, 하위 문제의 수에 비례합니다.

동적 프로그래밍은 복잡한 문제를 효율적으로 해결하기 위한 강력한 알고리즘 설계 기법으로, 다양한 분야에서 최적의 해법을 찾는 데 널리 사용됩니다.

---