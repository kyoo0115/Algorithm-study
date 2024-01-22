# 버블 정렬 (Bubble Sort)

## 버블 정렬이란?

버블 정렬은 기본적인 비교 기반 정렬 알고리즘입니다. 이 알고리즘은 인접한 두 요소를 비교하고, 필요한 경우 위치를 교환하여 정렬을 수행합니다. 버블 정렬은 이해하기 쉽고 구현하기 간단하지만, 대규모 데이터셋에는 비효율적일 수 있습니다.

## 코드 예제 (Java)

```java
public class BubbleSort {
    public static void sort(int[] array) {
        int n = array.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n -i - 1; j++) {
                if (array[j] > array[j + 1]) {
                    // 요소들의 위치를 교환
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
    }
}
```

## 시간 복잡도와 공간 복잡도
- 시간 복잡도: 최악의 경우 및 평균적인 경우 <b>O(n²)</b>, 최선의 경우 <b>O(n)</b>
- 공간 복잡도: <b>O(1)</b> (부가적인 공간 사용이 없음)
