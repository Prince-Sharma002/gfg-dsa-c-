# Find a pair with given target in BST

```
    void Inorder( struct Node* root , int target , vector<int>& ans )
    {
        if( !root )
            return ;
        
        Inorder( root->left , target , ans );
        ans.push_back( root->data );
        Inorder( root->right , target , ans );
        
    }
    
    int isPairPresent(struct Node *root, int target)
    {
        // Inorder travesal of bst is sorted
        vector<int> ans;
        Inorder( root , target , ans );
        
        // by using double pointer method find target sum
        int s = 0 ; int e = ans.size() - 1;
        while( s < e ){
            if( ans[s] + ans[e] == target )
                return 1;
            if( ans[s] + ans[e] < target )
                s++;
            else
                e--;
        }
        
        return 0;
        
    }
```
