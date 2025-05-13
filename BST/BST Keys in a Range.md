```
Input:
       17
     /    \
    4     18
  /   \
 2     9 
l = 4, h = 24
Output: 
4 9 17 18 
```

```
    void solve( Node* root , int low , int high , vector<int>& ans ){
        if( !root ) return ;
        if( root->data >= low && root->data <= high ){
            ans.push_back( root->data );
        }
        
        if( root->data > low )
            solve( root->left , low , high , ans );
        
        if( root->data < high )
            solve( root->right , low , high , ans );
        return ;
    }
    
    vector<int> printNearNodes(Node *root, int low, int high) {
        vector<int> ans;
        solve( root , low , high , ans );
        sort( ans.begin() , ans.end());
        return ans;
    }
```
