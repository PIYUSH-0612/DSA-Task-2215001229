```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int[]  mergedArray = new int[nums1.length + nums2.length];

        int index = 0;

        for (int i = 0; i < nums1.length; i++) {
            mergedArray[index] = nums1[i];
            index++;
        }

        for (int j = 0; j < nums2.length; j++) {
            mergedArray[index] = nums2[j];
            index++;
        }
        Arrays.sort(mergedArray);
        double result;
        if(mergedArray.length %2==0){
            result=(mergedArray[mergedArray.length/2]+mergedArray[(mergedArray.length/2)-1])/2d;
        }
        else{
            result=mergedArray[mergedArray.length/2];
        }
        return result;
    }
}
```