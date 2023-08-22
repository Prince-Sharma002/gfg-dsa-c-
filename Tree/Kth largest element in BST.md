# Kth largest element in BST

```
    void solve( Node* root , vector<int> &ans){
        if( root == NULL )
            return ;
        
        solve( root->left , ans );
        ans.push_back( root->data );
        solve( root->right , ans );
        
        
    }
    int kthLargest(Node *root, int K)
    {
        vector<int> ans;
        solve( root , ans );
        return ans[ans.size() - K  ];
    }
```
