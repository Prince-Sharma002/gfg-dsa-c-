# Smallest number on left
### Example
```
Input: n = 3
a = {1, 6, 2}
Output: -1 1 1
Explaination: There is no number at the 
left of 1. Smaller number than 6 and 2 is 1.
```

### Code
```
  vector<int> leftSmaller(int n, int a[]){
      stack<int> st;
      vector<int> ans;
      for( int i=0 ; i<n ; i++ ){
              while( !st.empty() && st.top() >= a[i] )
                  st.pop();
              
              if( st.empty() ){
                  st.push( a[i] );
                  ans.push_back( -1 );
                  continue;
              }
              
              ans.push_back(st.top());
              st.push( a[i] );
      }
      
      return ans;
  }
```











