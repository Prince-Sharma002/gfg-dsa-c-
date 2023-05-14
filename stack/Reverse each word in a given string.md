# Reverse each word in a given string
### Example
```
Input:
S = "i.like.this.program.very.much"
Output: 
i.ekil.siht.margorp.yrev.hcum

Expected Time Complexity:O(|S|).
Expected Auxiliary Space:O(|S|).
```

### Code
```
string reverseWords (string s)
{
    stack<char> st;
    string str = "";
    for( int i=0 ; i<s.size() ; i++ ){
        if( s[i]  == '.' ){
            while(st.size() != 0){
                str = str + st.top();
                st.pop();
            }
            str = str + ".";
        }
        else{
            st.push( s[i] );
        }
    }
    
    
    while(st.size() != 0){
        str = str + st.top();
        st.pop();
    }
    
    return str;
}
```











