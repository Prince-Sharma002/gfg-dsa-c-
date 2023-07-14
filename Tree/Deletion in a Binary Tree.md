
# Deletion in a Binary Tree

```

void deleteLastNode( struct Node* root , struct Node* lastNode ){
    queue<Node*> q;
    q.push( root );
    
    while( !q.empty() ){
        Node* temp = q.front();
        q.pop();
        if( temp->left ){
            if( temp->left == lastNode )
            {
                temp->left = NULL;
                return ;
            }
            else
                q.push( temp->left );
        }
        
        if( temp->right ){
            if( temp->right == lastNode )
            {
                temp->right = NULL;
                return ;
            }
            else
                q.push( temp->right );
        }
        
    }
}


struct Node* deletionBT(struct Node* root, int key)
{
     queue<Node*> q;
     q.push( root );
     Node* dNode = NULL;
     Node* temp;
     while( !q.empty() ){
         temp = q.front();
         q.pop();
         if( temp->data == key ) 
            dNode = temp;
         if( temp->left ) q.push( temp->left );
         if( temp->right ) q.push( temp->right );
     }
     
     int x = temp->data;
     deleteLastNode( root , temp );
     dNode->data = x;
    
    return root;
}
```



