# Expression contains redundant bracket or not
### Example
```
Input: str = “(a+(b)/c)”
Output: YES
Explanation: (a+(b)/c) can reduced to (a+b/c) because b is surrounded by () which is redundant.
```

### Code
```
bool redundant( string str ){
    stack<char> st;
    int c = 0;
    for( int i=0 ; i<str.size() ; i++ ){
        
        if( str[i] == '(' || str[i] == '+' || str[i] == '-' || str[i] == '*' ||  str[i] == '/' )
            st.push( str[i] );
        else if( str[i] == ')' ){
            while( st.top() != '(' ){
                c++;
                st.pop();
            }
            if( c != 0 ){
                st.pop();
                c = 0;
            }
            else
                return 1;
        }   
    }
    return 0;
}


int main() {
	string str = "((a+b)+c) ";

    if( redundant( str )  )
        cout << "Redundant braces";
    else 
        cout << "Not redundant braces";
}
```











