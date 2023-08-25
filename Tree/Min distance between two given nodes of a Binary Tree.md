# Min distance between two given nodes of a Binary Tree

```
    Node* lca(Node* root , int a , int b ){
        if( !root )
            return NULL;
            
        if( root->data == a || root->data == b )
            return root;
        
        Node* leftLca = lca( root->left , a , b );
        Node* rightLca = lca( root->right , a , b );
        
        if( leftLca && rightLca )
            return root;
        else if( leftLca )
            return leftLca;
        else 
            return rightLca;
        
    }
    
    
    int distance( Node* root , int key , int h ){
        if( !root )
            return -1;
        
        if( root->data == key )
            return h;
        
        int left = distance( root->left , key , h+1 );
        
        // if left is -1 that means element not find in leftsubtree 
        if( left == -1 )
            return distance( root->right , key , h+1 );
        
        
        
    }
    
    
    int findDist(Node* root, int a, int b) {
            Node* commonNode = lca( root , a , b );
            int lh = distance( commonNode , a , 0 );
            int rh = distance( commonNode , b , 0 );
            
            return lh + rh ;
            
    }
```
