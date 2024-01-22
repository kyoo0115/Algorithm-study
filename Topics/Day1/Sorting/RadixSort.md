# 기수 정렬 (Radix Sort)

## 기수 정렬이란?

기수 정렬은 비교하지 않는 정렬 알고리즘 중 하나로, 정수나 문자열과 같은 키 값을 가진 배열을 정렬하는 데 사용됩니다. 이 알고리즘은 키 값을 자릿수 별로 정렬하며, 가장 낮은 자릿수부터 가장 높은 자릿수까지 반복적으로 정렬합니다. 기수 정렬은 비교 기반 알고리즘과는 다른 방식으로 동작하여 정수나 문자열을 빠르게 정렬할 때 유용합니다.

## 정렬 과정 설명 및 다이어그램
- 기수 정렬은 키 값을 자릿수 별로 나누고 각 자릿수를 정렬합니다.
- 가장 낮은 자릿수부터 시작하여 가장 높은 자릿수까지 정렬을 반복합니다.

<img src= "./images/RadixSort.png" width="1156">

- 배열의 가장 낮은 자릿수를 기반으로 정렬합니다.
- 정렬된 결과를 다음 자릿수로 이어질 정렬에 사용합니다.
- 가장 높은 자릿수까지 이 과정을 반복하여 배열이 정렬됩니다.

## 코드 예제 (Java)

```java
public class RadixSort {

    public static void radixSort(int[] array) {
        int max = findMax(array);
        int digitPlace = 1;
        
        while (max / digitPlace > 0) {
            countingSort(array, digitPlace);
            digitPlace *= 10;
        }
    }

    private static void countingSort(int[] array, int digitPlace) {
        final int radix = 10; // 기수 (0-9까지)
        int[] countArray = new int[radix];
        int[] outputArray = new int[array.length];

        for (int value : array) {
            int digit = (value / digitPlace) % radix;
            countArray[digit]++;
        }

        for (int i = 1; i < radix; i++) {
            countArray[i] += countArray[i - 1];
        }

        for (int i = array.length - 1; i >= 0; i--) {
            int digit = (array[i] / digitPlace) % radix;
            outputArray[countArray[digit] - 1] = array[i];
            countArray[digit]--;
        }

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
}
```

## 시간 복잡도와 공간 복잡도
- 시간 복잡도: 모든 경우에 <b>O(nk)</b> (n: 배열의 크기, k: 가장 큰 자릿수)
- 공간 복잡도: <b>O(n+k)</b> (n: 배열의 크기, k: 기수)