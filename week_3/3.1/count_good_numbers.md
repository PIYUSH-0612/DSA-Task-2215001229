```java
class Solution {
    int MOD = (int) (Math.pow(10, 9) + 7);
    public long mod(long a, long b) {
        return ((a%MOD) * (b%MOD))%MOD;
    }
    public int power(int a, long n) {
        if(n == 0)
            return 1;
        long ans = power(a, n/2);
        ans = mod(ans, ans);
        if(n%2==0)
            return (int)ans;
        return (int)mod(ans, a);
    }
    public int countGoodNumbers(long n) {
        if(n==1)
            return 5;
        if(n%2==0)
            return power(20, n/2);
        return (int)mod(power(20, n/2) ,5);
    }
}
```