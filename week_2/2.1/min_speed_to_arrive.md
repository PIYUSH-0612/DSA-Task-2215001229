```java
class Solution {
    public int minSpeedOnTime(int[] dist, double hour) {
        int st = 1;
        int end = 10000000;

        while(st < end){
            int mid = (st + end)/2;
            if(check(dist,mid,hour)){
                end = mid;
            }
            else{
                st = mid +1;
            }
        }
        int ans = 0;

        if(check(dist,st,hour)){
            ans = st;
        }else{
            ans = -1;
        }
        return ans;
    }

    public boolean check(int[] dist,int speed,double hour){
        double time = 0.0;

        for(int i=0;i<dist.length;i++){
            double t = (double) dist[i]/speed;
            if(i == dist.length -1){
                time += t;
            }
            else{
                time += Math.ceil(t);
            }
            
        }
        return time <= hour;
    }
}
```