# 힙 정렬 (Heap Sort)

## 힙 정렬이란?

힙 정렬은 효율적인 비교 기반 정렬 알고리즘으로, 힙(Heap) 자료구조를 사용하여 정렬합니다. 이 알고리즘은 배열을 힙으로 만든 다음 최대 힙(또는 최소 힙)에서 요소를 추출하여 정렬합니다. 힙 정렬은 안정적인 정렬 방법으로, 대규모 데이터셋에 효과적입니다.

## 정렬 과정 설명 및 다이어그램
- 힙 정렬은 주어진 배열을 최대 힙(또는 최소 힙)으로 만듭니다.
- 최대 힙(또는 최소 힙)에서 루트 요소를 추출하고 배열의 끝에 배치합니다.
- 힙 크기를 줄이고 힙을 다시 구성하여 다음 최대(또는 최소) 요소를 추출합니다.
- 이 과정을 반복하여 배열이 정렬됩니다.

<img src= "./images/HeapSort.png" width="1156">

- 배열을 최대 힙으로 만들기 위해 루트부터 시작하여 요소들을 아래로 힙 구조에 맞게 재배열합니다.
- 최대 힙에서 루트 요소를 추출하여 배열의 끝에 배치합니다.
- 힙 크기를 줄이고 힙을 다시 구성하여 다음 최대 요소를 추출합니다.
- 이 과정을 반복하여 배열이 정렬됩니다.

## 코드 예제 (Java)

```java
public class HeapSort {

    public static void heapSort(int[] array) {
        int n = array.length;

        // 배열을 최대 힙으로 만듭니다.
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(array, n, i);
        }

        // 힙에서 요소를 하나씩 추출하여 정렬합니다.
        for (int i = n - 1; i >= 0; i--) {
            int temp = array[0];
            array[0] = array[i];
            array[i] = temp;

            heapify(array, i, 0);
        }
    }

    private static void heapify(int[] array, int n, int i) {
        int largest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;

        if (left < n && array[left] > array[largest]) {
            largest = left;
        }

        if (right < n && array[right] > array[largest]) {
            largest = right;
        }

        if (largest != i) {
            int swap = array[i];
            array[i] = array[largest];
            array[largest] = swap;

            heapify(array, n, largest);
        }
    }
}
```
## 시간 복잡도와 공간 복잡도
- 시간 복잡도: 모든 경우에 <b>O(n log n)</b>
- 공간 복잡도: <b>O(1)</b> (부가적인 공간 사용이 없음)