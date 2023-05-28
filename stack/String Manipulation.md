# String Manipulation
### Example
```
Input:
4
v[] = {"tom", "jerry", "jerry", "tom"}
Output:
0
Explanation:
tom jerry jerry tom
```

### Code
```
stack<string> st;
int removeConsecutiveSame(vector <string > v) 
{
    for( int i=0 ; i<v.size() ; i++ ){
         if( st.empty() ){
             st.push( v[i] );
             continue;
         }
         
         if( st.top() == v[i] )
            st.pop();
         else
            st.push( v[i] );
         
    }
    
    return st.size();
} 
```











