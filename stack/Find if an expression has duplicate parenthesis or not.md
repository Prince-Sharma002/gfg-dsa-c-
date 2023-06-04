# Find if an expression has duplicate parenthesis or not
### Example
```
((a+b)+((c+d)))
The subexpression "c+d" is surrounded by two
pairs of brackets.
```

### Code
```
#include <bits/stdc++.h>
using namespace std;

bool duplicate( string str ){
    stack<char> st; 
    for( int i=0 ; i<str.size() ; i++ ){
        if( str[i] == '(' )
            st.push( '(' );
        else if( str[i] == ')' ){
            if( st.top() != 's' )
                    return 1;
                    
            while( st.top() != '(' ){
                st.pop();
            }
            st.pop();
        }
        else
            st.push( 's' );
        
    }
    return 0;
}


int main() {
	string str = "((a+b)+(c+d))";

    if( duplicate( str )  )
        cout << "duplicate braces";
    else 
        cout << "Not duplicate braces";
}
```











