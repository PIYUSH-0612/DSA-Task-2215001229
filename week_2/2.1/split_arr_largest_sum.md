```java
class Solution {
    public int splitArray(int[] nums, int m) {
        int left = 0;
        int right = 0;

        for (int i : nums) {
            left = Math.max(left, i);
            right += i;
        }

        while (left < right) {
            int mid = left + (right - left) / 2;

            if (check(nums, m, mid)) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }

        return left;
    }

    private boolean check(int[] nums, int m, int maxSum) {
        int sum = 0;
        int div = 1;

        for (int i : nums) {
            if (sum + i > maxSum) {
                sum = i;
                div++;
                if (div > m)
                    return false;
            } else {
                sum += i;
            }
        }

        return true;
    }
}

```