```java
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        int[] ans = new int[nums1.length];
        int ind = 0;
        for (int i:nums1) {
            int idx = 0;
            for (int j = 0; j < nums2.length; j++) {
                if (nums2[j] == i) {
                    idx = j;
                    break;
                }
            }
            int nxt = -1;
            for (int k = idx + 1; k < nums2.length; k++) {
                if (nums2[k] > i) {
                    nxt = nums2[k];
                    break;
                }
            }
            ans[ind] = nxt;
            ind++;
        }
        
        return ans;
    }
}

```