# Children Sum Parent

```
    int isSumProperty(Node *root)
    {
    int sum = 0;
     if( !root || !root->left && !root->right )
        return 1;
    else{
        if( root->left )
            sum += root->left->data;
        if( root->right )
            sum += root->right->data;
        return  root->data == sum &&
            isSumProperty(root->left) && isSumProperty( root->right);            
    }
    
    return 0;
     
    }
```
