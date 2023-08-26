# Maximum sum leaf to root path

```
    int solve( Node* root ){
        if( !root   )
            return 0;
            
        
        int ls = maxPathSum( root->left );
        int rs = maxPathSum( root->right );
        
        if( ls == 0 )
            return rs + root->data;
        else if( rs == 0 )
            return ls + root->data;
            
        return max( ls , rs ) + root->data ;
    }
    
    int maxPathSum(Node* root)
    {
        return solve( root );
    }
```
