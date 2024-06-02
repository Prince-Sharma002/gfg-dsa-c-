```
void solve( Node* node , int data){
            if( node->data == data )
                return ;
            
            if( node->data  < data )
            {
                if( node->right == NULL ){
                    node->right = new Node(data);
                    return ;
                }
                else
                    solve( node->right , data );
            }
            else{
                if( node->left == NULL ){
                    node->left = new Node(data);
                    return ;
                }
                else
                    solve( node->left , data );
            }
}

        Node* insert(Node* node, int data) {
        
            solve( node , data );
            return node;
            
    }

```
