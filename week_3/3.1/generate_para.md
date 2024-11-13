```java
class Solution {
    
    public List<String> generateParenthesis(int n) {
        List<String> list=new ArrayList<>();
            print(n,0,0,"",list);
            return list;
        }
        private static void print(int n,int open,int close,String ans,List<String> list){
            if(open==n && close==n){
                list.add(ans);
                return;
            }
            if(open<n){
                print(n,open+1,close,ans+"(",list);
            }
            if(close<open){
                print(n,open,close+1,ans+")",list);
            }
        }
    }

```