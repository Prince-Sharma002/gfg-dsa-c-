# Reverse a Stack
### Example
```
Input:
St = {3,2,1,7,6}
Output:
{6,7,1,2,3}

Expected Time Complexity: O(N)
Expected Auxiliary Space: O(N)
```

### Code
```
void reverse( stack<int> &st , stack<int> &st2 ){
    
      if(st.size() == 0)
        return ;
        
      int t = st.top();
      st.pop();
      reverse(st , st2);
      
      st2.push(t);
      
}
void Reverse(stack<int> &st){
    
      stack<int> st2;
      reverse(st , st2);
      
      while(st2.size() != 0){
        st.push( st2.top() );
        st2.pop();
      }

}
```











