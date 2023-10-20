# Infix to Postfix

```
    // Function to convert an infix expression to a postfix expression.
    string infixToPostfix(string s) {
        string ans = "";
        stack<char> st;
        unordered_map<char , int> prec;
        prec['^'] = 3;
        prec['*'] = 2;
        prec['/'] = 2;
        prec['+'] = 1;
        prec['-'] = 1;
        
        s = '(' + s + ')';
        
        for( int i=0 ; i<s.length() ; i++ ){
            char ch = s[i];
            if( isalpha(ch) || isdigit(ch) ){
                ans += ch;
            }
            else if( ch == '(')
                st.push('(');
            else if( ch == ')')
            {
                while( !st.empty() && st.top() != '(')
                {
                    ans += st.top();
                    st.pop();                    
                }
                st.pop();
            }    
            else{
                while( !st.empty() && prec[ch] <= prec[ st.top() ] ){
                    ans += st.top();
                    st.pop();
                }
                st.push(ch);
            }
            
        }   
        
        
        return ans;
    }
```
