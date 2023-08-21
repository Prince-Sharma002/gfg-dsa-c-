# Symmetric Tree
```
    // return true/false denoting whether the tree is Symmetric or not
    bool isMirror( struct Node *r1 , struct Node *r2)
    {
        if( !r1 && !r2 )
            return true;
        
        if( r1 && r2 ){
            return (r1->data == r2->data) && isMirror(r1->left , r2->right)
                && isMirror(r1->right , r2->left); 
        }
        
        return 0;
        
    }
    
    bool isSymmetric(struct Node* root)
    {
        return isMirror( root , root );
    }
```
