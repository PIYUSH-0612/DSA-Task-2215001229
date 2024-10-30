```java
class Solution {
    public int[] searchRange(int[] nums, int target) {
        int[] ans=new int[2];
        int start=-1;
        int end=-1;
        if(nums.length==0){
            start=-1;
            end=-1;
        }
        for(int i=0;i<nums.length;i++){
            if(nums[i]==target){
                start=i;
                break;
            }
        }
        for(int i=nums.length-1;i>=0;i--){
            if(nums[i]==target){
                end=i;
                break;
            }
        }

        ans[0]=start;
        ans[1]=end;

        return ans;
    }
}
```