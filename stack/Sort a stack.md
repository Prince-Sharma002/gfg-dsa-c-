# Sort a stack
### Example
```
Input:
Stack: 11 2 32 3 41
Output: 41 32 11 3 2
```

### Code
```
void SortedStack :: sort()
{
  stack<int> st;

    
  while( !s.empty() ){
      if(s.empty())
        return ;
      
      int temp = s.top();
      s.pop();
      int a = 0;    
        
         while( !st.empty() && st.top() < temp  ){
             s.push( st.top() );
             st.pop();
             a++;
         }
         st.push( temp );
         while( !s.empty() &&  a > 0    ){
             a--;
             st.push(s.top());
             s.pop();
         }
  }
  
  while( !st.empty() ){
      s.push( st.top() );
      st.pop();
  }
}
```











