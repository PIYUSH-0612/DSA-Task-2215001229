```java
class Solution {
    public String removeOuterParentheses(String s) {
       Stack<Character> st = new Stack<>(); 
        int open = 1;
        int close = 0;
       for (int i = 1; i < s.length(); i++){
        char c = s.charAt(i);
        if( c == '('){
            open++;
            st.push(c);
        }else{
            close++;
            st.push(c);
        }
        if(open == close){
            st.pop();
            close = 0;
            open = 1;
            i++;
        }

       }
        String ans = "";
       while(!st.isEmpty()){
        ans = st.pop()+ans;
       }
       return ans;
    }
}
```