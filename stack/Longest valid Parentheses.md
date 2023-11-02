# Longest valid Parentheses


```
    int maxLength(string str){
            
        int ans = 0;
        stack<int> st;
        st.push(-1);
        for( int i=0 ; i<str.length() ; i++ ){
            if( str[i] == '(' )
                st.push(i);
            else{
                
                if( !st.empty() )
                    st.pop();
                
                if( !st.empty() ){
                    ans = max( ans , i - st.top() );
                }
                else
                    st.push( i );
                
            }
        }
    
        return ans;        
    }

```
