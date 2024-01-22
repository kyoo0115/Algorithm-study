# 쉘 정렬 (Shell Sort)

## 쉘 정렬이란?

쉘 정렬은 삽입 정렬의 변형으로, 효율적인 비교 기반 정렬 알고리즘 중 하나입니다. 이 알고리즘은 배열을 여러 부분 배열로 나누고 각 부분을 삽입 정렬로 정렬한 다음, 부분 배열을 합치는 방식을 사용하여 정렬합니다. 쉘 정렬은 중간 크기의 데이터셋에 적합하며 빠른 정렬 성능을 제공합니다.

## 정렬 과정 설명 및 다이어그램
- 쉘 정렬은 배열을 여러 부분 배열로 나눈 후, 각 부분을 삽입 정렬로 정렬합니다.
- 부분 배열의 크기는 일정한 간격(간격 시퀀스)을 가지며, 정렬 과정에서 간격을 줄여가며 정렬을 수행합니다.

<img src= "./images/ShellSort.png" width="1156">

- 배열을 여러 부분 배열로 나눕니다.
- 각 부분 배열을 삽입 정렬로 정렬합니다.
- 부분 배열의 크기(간격)를 줄여가며 정렬을 반복합니다.
- 모든 부분 배열이 하나로 합쳐질 때까지 이 과정을 반복합니다.

## 코드 예제 (Java)

```java
public class ShellSort {

    public static void shellSort(int[] array) {
        int n = array.length;
        for (int gap = n / 2; gap > 0; gap /= 2) {
            for (int i = gap; i < n; i++) {
                int temp = array[i];
                int j;
                for (j = i; j >= gap && array[j - gap] > temp; j -= gap) {
                    array[j] = array[j - gap];
                }
                array[j] = temp;
            }
        }
    }
}
```

## 시간 복잡도와 공간 복잡도
- 시간 복잡도: 최악의 경우 <b>O(n²)</b>, 최선의 경우 <b>O(nlogn)</b>
- 공간 복잡도: <b>O(1)</b> (부가적인 공간 사용이 없음)