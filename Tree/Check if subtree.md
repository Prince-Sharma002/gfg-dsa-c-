# Check if subtree

```
  bool isSame( Node* T , Node* S ){
            
        if (T == NULL && S == NULL)
            return true;
 
        if (T == NULL || S == NULL)
            return false;
        
            
        if( T && S )
            return T->data == S->data && isSame( T->left , S->left ) && 
                    isSame( T->right , S->right );
        return 0;
    }
    
    
    bool isSubTree(Node* T, Node* S) 
    {
        if( !T )
            return 0;
        if( !S )
            return 1;
            
        if( isSame(T , S))
            return 1;
        
        
        return isSubTree(T->left , S) || isSubTree(T->right , S);
        
    }
```
