# Clone a Binary Tree

```
    void clone( Node* root1 , Node* root2  ){
        if( !root1 )
            return ;
            
        if( root1->random ){
            root2->random = root1->random;
        }
        
        if( root1->left){
            Node* node = new Node( root1->left->data );
            root2->left = node;
            clone( root1->left , root2->left);
        }
        if( root1->right ){
            Node* node = new Node( root1->right->data );
            root2->right = node;
            clone( root1->right , root2->right);
        }
        
    }
    
    Node* cloneTree(Node* tree)
    {
       Node* root2 = new Node( tree->data );
       clone( tree , root2 );
       
       return root2;
    }
```
