# Evaluation of Postfix Expression

```
    //Function to evaluate a postfix expression.
    int evaluatePostfix(string S)
    {
        // Your code heref
        stack<int> st;
        for( int i=0 ; i<S.length() ; i++ ){
            char ch = S[i];
            if( isdigit(ch) ){
                st.push( ch - '0' );
            }
            else{
                if( st.size() >= 2 ){
                    int s = st.top();
                    st.pop();
                    int f = st.top();
                    st.pop();
                    if( ch == '*' )
                        st.push(f*s);
                    else if( ch == '+' )
                        st.push( f+s );
                    else if( ch == '-' )
                        st.push( f-s );
                    else if( ch == '/' )
                        st.push( f/s );
                }
            }
            
        }
        if( st.top() )
            return st.top();
    }
```
