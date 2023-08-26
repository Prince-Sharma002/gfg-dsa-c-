# Remove BST keys outside given range

```
    Node* removekeys(Node* root, int l, int r) {
        if( !root )
            return NULL;
        
        root->left = removekeys( root->left , l , r );
        root->right = removekeys( root->right , l , r );
        
        if( root->data < l ){
            Node* leftnode = root->right;
            delete root;
            return leftnode;
        }
        
        if( root->data > r ){
            Node* rightnode = root->left;
            delete root;
            return rightnode;
        }
        return root;
        
    }
```
