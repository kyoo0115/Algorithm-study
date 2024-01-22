# 계수 정렬 (Counting Sort)

## 계수 정렬이란?

계수 정렬은 정수나 정수 키를 가진 배열을 정렬하는 데 사용되는 비교하지 않는 정렬 알고리즘입니다. 이 알고리즘은 키 값의 범위를 알고 있을 때 가장 효과적으로 작동하며, 특히 큰 범위의 정수 데이터를 정렬할 때 유용합니다. 계수 정렬은 각 키 값의 출현 빈도를 계산하고 정렬된 배열을 만드는 방식으로 동작합니다.

## 정렬 과정 설명 및 다이어그램
- 계수 정렬은 정렬하려는 배열의 키 값을 기반으로 각 키 값의 출현 빈도를 계산합니다.
- 출현 빈도를 사용하여 각 키 값을 정렬된 배열의 적절한 위치에 배치합니다.

<img src= "./images/CountingSort.png" width="1156">

- 배열의 모든 요소의 출현 빈도를 계산합니다.
- 출현 빈도를 사용하여 각 키 값을 정렬된 배열의 올바른 위치에 배치합니다.

## 코드 예제 (Java)

```java
public class CountingSort {

    public static void countingSort(int[] array) {
        int max = findMax(array);
        int min = findMin(array);
        int range = max - min + 1;
        
        int[] countArray = new int[range];
        int[] outputArray = new int[array.length];

        // 출현 빈도 계산
        for (int value : array) {
            countArray[value - min]++;
        }

        // 출현 빈도를 누적 합으로 변경
        for (int i = 1; i < range; i++) {
            countArray[i] += countArray[i - 1];
        }

        // 정렬된 배열 생성
        for (int i = array.length - 1; i >= 0; i--) {
            outputArray[countArray[array[i] - min] - 1] = array[i];
            countArray[array[i] - min]--;
        }

        // 정렬된 배열 복사
        System.arraycopy(outputArray, 0, array, 0, array.length);
    }

    private static int findMax(int[] array) {
        int max = array[0];
        for (int value : array) {
            if (value > max) {
                max = value;
            }
        }
        return max;
    }

    private static int findMin(int[] array) {
        int min = array[0];
        for (int value : array) {
            if (value < min) {
                min = value;
            }
        }
        return min;
    }
}
```

## 시간 복잡도와 공간 복잡도
- 시간 복잡도: <b>O(n + k)</b> (n: 배열의 크기, k: 정수의 범위)
- 공간 복잡도: <b>O(n + k)</b> (n: 배열의 크기, k: 정수의 범위)