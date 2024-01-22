# 퀵 정렬 (Quick Sort)

## 퀵 정렬이란?

퀵 정렬은 효율적인 비교 기반 분할 정복 정렬 알고리즘입니다. 이 알고리즘은 '피벗'을 기준으로 배열을 분할하고, 각 부분을 재귀적으로 정렬하는 방식을 사용합니다. 퀵 정렬은 평균적으로 빠른 성능을 제공하며, 대규모 데이터셋에 효과적입니다.

## 정렬 과정 설명 및 다이어그램
- 퀵 정렬은 피벗을 기준으로 배열을 분할하고, 각 부분을 재귀적으로 정렬하는 방식입니다. 이 과정은 배열이 완전히 정렬될 때까지 반복됩니다.

<img src= "./images/QuickSort.png" width="1156">

- 배열에서 피벗을 선택합니다 (일반적으로 첫 번째 또는 마지막 요소).
- 피벗보다 작은 요소는 피벗의 왼쪽, 큰 요소는 오른쪽으로 이동합니다.
- 피벗을 기준으로 배열을 두 부분으로 나눕니다.
- 각 부분에 대해 동일한 과정을 재귀적으로 반복합니다.

## 코드 예제 (Java)

```java
public class QuickSort {

    public static void quickSort(int[] array, int low, int high) {
        if (low < high) {
            int pi = partition(array, low, high);

            quickSort(array, low, pi - 1);
            quickSort(array, pi + 1, high);
        }
    }

    private static int partition(int[] array, int low, int high) {
        int pivot = array[high];
        int i = (low - 1);
        for (int j = low; j < high; j++) {
            if (array[j] < pivot) {
                i++;

                int temp = array[i];
                array[i] = array[j];
                array[j] = temp;
            }
        }

        int temp = array[i + 1];
        array[i + 1] = array[high];
        array[high] = temp;

        return i + 1;
    }
}
```

## 시간 복잡도와 공간 복잡도
- 시간 복잡도: 최악의 경우 <b>O(n²)</b>, 평균적인 경우 <b>O(nlogn)</b>
- 공간 복잡도: <b>O(logn)</b> (재귀 호출에 필요한 공간)