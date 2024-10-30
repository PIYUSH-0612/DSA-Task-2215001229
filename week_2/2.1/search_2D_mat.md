```java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int r = matrix.length;
        int c = matrix[0].length;
        int row = 0;
        int col = c - 1;

        while(row < r && col > -1){
            int cur = matrix[row][col];
            if(cur == target){
                return true;
            }
            if(target > cur){
                row++;
            }
            else{
                col--;
            }
        }
        return false;
    }
}
```