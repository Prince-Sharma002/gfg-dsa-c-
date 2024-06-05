# Kth largest element in BST

```
    void solve( Node* root , int K , vector<int> &ans  ){
        if( !root )
            return ;
        
        solve( root->left , K , ans );
        ans.push_back( root->data );
        solve( root->right , K , ans );
    }
    
    int KthSmallestElement(Node *root, int K) {
        vector<int> ans;
        solve( root , K , ans );
        
        if( K > ans.size() )
            return -1;
        
        return ans[  K -1 ];
        
        
    }
```
