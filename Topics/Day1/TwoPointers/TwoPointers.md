# 투 포인터 (Two Pointers)

---

## 투 포인터란?

투 포인터는 배열 또는 리스트에서 두 개의 포인터를 사용하여 특정 문제를 해결하는 알고리즘 기법입니다. 
투포인터는 주로 배열이나 리스트를 순차적으로 탐색하거나 특정 조건을 만족하는 부분을 찾는데 사용됩니다. 
이 알고리즘은 대부분의 경우 시간 복잡도가 선형이며 공간 복잡도가 상수입니다.

## 예제 1: 배열에서 합이 특정 값인 두 숫자 찾기

```java
public class TwoPointersExample1 {

    public static int[] findTwoSum(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;

        while (left < right) {
            int sum = nums[left] + nums[right];

            if (sum == target) {
                return new int[]{left, right};
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }

        return new int[]{-1, -1}; // 찾을 수 없음
    }
}
```
- 이 예제에서 투 포인터는 배열 nums에서 합이 target인 두 숫자의 인덱스를 찾습니다. 배열은 정렬되어 있어야 합니다.

## 예제 2: 배열에서 세 숫자의 합이 특정 값인 경우 찾기
```java
import java.util.*;

public class TwoPointersExample2 {

    public static List<List<Integer>> findThreeSum(int[] nums, int target) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);

        for (int i = 0; i < nums.length - 2; i++) {
            if (i > 0 && nums[i] == nums[i - 1]) {
                continue; // 중복된 요소 건너뛰기
            }

            int left = i + 1;
            int right = nums.length - 1;

            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];

                if (sum == target) {
                    result.add(Arrays.asList(nums[i], nums[left], nums[right]));
                    while (left < right && nums[left] == nums[left + 1]) left++;
                    while (left < right && nums[right] == nums[right - 1]) right--;
                    left++;
                    right--;
                } else if (sum < target) {
                    left++;
                } else {
                    right--;
                }
            }
        }

        return result;
    }
}
```

- 이 예제에서 투 포인터는 배열 nums에서 합이 target인 세 숫자 조합을 찾습니다. 배열은 정렬되어 있어야 하며 중복된 조합을 제거합니다.
- 투 포인터 알고리즘은 배열 또는 리스트에서 두 개의 포인터를 사용하여 다양한 문제를 효과적으로 해결할 수 있습니다.
- 단, 정렬이 된 배열 또는 리스트에서만 사용할 수 있습니다.
## 문제 출처: 
1. [LeetCode - Two Sum](https://leetcode.com/problems/two-sum/)
2. [LeetCode - 3Sum](https://leetcode.com/problems/3sum/)