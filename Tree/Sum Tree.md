# Sum Tree

```
    int flag = 1;
    int solve( Node* root  ){
        if( !root )
            return 0;
        
        if( !root->left && !root->right )
            return root->data;
        
        if( root->data == solve(root->left ) + solve( root->right ))
            return root->data * 2;
        else
            {
                flag = 0;
                return -1;
            }
             
        
    }
    bool isSumTree(Node* root)
    {
        solve( root );
        return flag;
    }
```
