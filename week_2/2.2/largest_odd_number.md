```java
class Solution {
    public String largestOddNumber(String num) {
        String Str_ones = String.valueOf(num.charAt(num.length()-1));
        int ones = Integer.parseInt(Str_ones);

        if(ones%2 != 0){
            return num;
        }

        String ans = "";

        for(int i = num.length()-1;i>=0;i--){
            String temp = String.valueOf(num.charAt(i));
            int curr = Integer.parseInt(temp);
            if(curr%2 == 0){
                ans = num.substring(0,i);
            }
            else{
                return ans;
            }
        }
        return ans;
    }
}
```