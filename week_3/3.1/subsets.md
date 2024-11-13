```java
class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        print(nums, 0, new ArrayList<>(), res);
        return res;
    }
    
    private void print(int[] nums, int idx, List<Integer> ls, List<List<Integer>> res) {
        res.add(new ArrayList<>(ls));
        
        for (int i = idx; i < nums.length; i++) {
            ls.add(nums[i]);
            print(nums, i + 1, ls, res);
            ls.remove(ls.size() - 1);
        }
    }
}

```