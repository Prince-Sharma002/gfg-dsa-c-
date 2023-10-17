# Parenthesis Checker

```
bool ispar(string x)
{
    stack<char> st;
    for (int i = 0; i < x.length(); i++) {
        char c = x[i];
        if (c == '(' || c == '{' || c == '[') {
            st.push(c);
        } else {
            // Check if the stack is empty before accessing top
            if (st.empty()) {
                return false;  // Stack is empty, so it's not balanced
            }
            
            char topChar = st.top();
            if ((c == ')' && topChar == '(') || (c == '}' && topChar == '{') || (c == ']' && topChar == '[')) {
                st.pop();  // Matching pair found, pop from the stack
            } else {
                return false;  // Mismatched characters
            }
        }
    }

    // If the stack is empty at the end, it means all pairs are matched
    return st.empty();
}
```
