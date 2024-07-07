```
Input:
         1
       /   \
      2     3
    /  \    /  \
   4   5  6   8
  /
 7
target = 7
Output: [4 2 1]
```

```
   
    void solve(  struct Node *root, int target , stack<int> &st , vector<int> &ans){
        if( root == NULL )
            return ;
        
        if( root->data == target )
        {
            while( !st.empty() ){
                ans.push_back( st.top() );
                st.pop();
            }
            return ;
        }
        
        st.push( root->data );
        
        solve( root->left , target , st , ans );
        solve( root->right , target , st , ans );
        
        if( !st.empty() )
            st.pop();
        
       
    }
    
    vector<int> Ancestors(struct Node *root, int target) {
        stack<int> st;
        vector<int> ans;
        solve( root , target , st , ans );
        
        return ans;
    }
```
