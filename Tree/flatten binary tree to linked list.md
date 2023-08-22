# Flatten a binary tree to linked list 
```
    void flatten(Node *root)
    {
        Node* curr = root;
        while( curr ){
            Node* Pred;
            if(curr->left)
            {
                Node* pred = curr->left;
                while( pred->right )
                    pred = pred->right;
                pred->right = curr->right;
                curr->right = curr->left;
                curr->left = NULL;
            }
            
            curr = curr->right;
                
        }
    }
```
