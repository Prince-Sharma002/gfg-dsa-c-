# Remove brackets from an algebraic string containing + and – operators
### Example
```
Input : "(a-(b+c)+d)"
Output : "a-b-c+d"

Input : "a-(b-c-(d+e))-f"
Output : "a-b+c+d+e-f" 
```

### Code
```
string remove_bracket( string str ){
    stack<char> st; 
    string ans = "";
    int i=0;
    char flag = '+';
    
    while( i <str.size() ) {
        
        if( st.empty() && isalpha( str[i] ) )
            ans = ans + str[i];
        else if( str[i] == '('){
            st.push( '(' ); st.push( '+' ); flag = '+' ;
        }
        else if( ( str[i] == '+' || str[i] == '-' ) && str[i+1] == '(' ){
            if( st.empty() ){
                st.push( '(' ); st.push( str[i] ); flag = str[i] ; i = i+1;
            }
            else{
                if( st.top() == '-' ){
                    st.push( '(' ); st.push( '+' ); flag ='+';  i = i+1;
                }
                else{
                    st.push( '(' ); st.push( '-' );  flag = '-'; i = i+1;
                }
            }
        }
        else if( isalpha( str[i] ) ){
            if( str[i-1] == '(' ){
                ans = ans + flag + str[i];
            }
            else
                ans = ans + str[i];
        }
        else if( ( str[i] == '+' || str[i] == '-' ) && str[i+1] != '(' ){
            if( str[i] != flag )    
                ans = ans + '-';
            else    
                ans = ans + '+';
        }
        else if( ')'  ){
            st.pop();
            st.pop();
            if( !st.empty() )
                flag = st.top();
            else 
                flag = '+';
   
        }

        
        i = i+1;
    }
    return ans;
}


int main() {
	string str = "a-(b-c-(d+e))-f";
    
    string ans = remove_bracket( str );
    
    cout << ans;
}

```











