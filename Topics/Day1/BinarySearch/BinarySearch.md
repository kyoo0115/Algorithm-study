# 이진 검색 (Binary Search)

## 이진 검색이란?

이진 검색은 정렬된 배열에서 원하는 값을 찾는 검색 알고리즘 중 하나입니다. 이 알고리즘은 배열을 반으로 나누어 중간 요소와 비교하며, 원하는 값을 찾을 때까지 반복합니다. 이진 검색은 매우 효율적이며, 배열이 정렬되어 있어야 합니다.

## 검색 과정 설명
- 이진 검색은 배열을 반으로 나눈 후 중간 요소와 비교합니다.
- 중간 요소가 원하는 값보다 작으면 검색 범위를 오른쪽 반쪽으로 제한하고, 크면 왼쪽 반쪽으로 제한합니다.
- 원하는 값을 찾을 때까지 위의 과정을 반복합니다.

## 코드 예제 (Java)

```java
public class BinarySearch {

    public static int binarySearch(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (array[mid] == target) {
                return mid; // 원하는 값 발견
            } else if (array[mid] < target) {
                left = mid + 1; // 오른쪽 반쪽에서 검색
            } else {
                right = mid - 1; // 왼쪽 반쪽에서 검색
            }
        }

        return -1; // 원하는 값이 배열에 없음
    }
}
```
## 시간 복잡도와 공간 복잡도
- 시간 복잡도: <b>O(log n)</b> (배열의 크기에 비례하지 않고, 매우 빠른 검색 속도를 제공)
- 공간 복잡도: <b>O(1)</b> (추가적인 공간 사용이 없음)