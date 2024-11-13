```java
class Solution {  
    public double myPow(double x, int n) {  
        if (n == 0) {  
            return 1;  
        }  
        if (n < 0) {  
            if (n == Integer.MIN_VALUE) {  
                x = 1 / x;  
                n = -(n + 1);  
                return (1 / x) * myPow(x, n); 
            }  
            x = 1 / x;  
            n = -n;  
        }  
        double ans = 1;  
        while (n > 0) {  
            if ((n % 2) == 1) {   
                ans *= x;  
            }  
            x *= x;   
            n /= 2;  
        }  
        return ans;  
    }  
}
```