# Ancestors in Binary Tree

```
    bool solve( struct Node* root , int target , vector<int>& ans ){
        if( !root )
            return 0;
        if( root->data == target )
            return 1;
        
        bool left = solve( root->left , target , ans );
        bool right = solve( root->right , target , ans);
        
        if( left )
            ans.push_back( root->data );
        if( right )
            ans.push_back( root->data );
        
    }
    
    vector<int> Ancestors(struct Node *root, int target)
    {
         vector<int> ans;
         solve( root , target , ans );
         return ans;
    }
```
