# Left View of Binary Tree

```
vector<int> leftView(Node *root)
{
    vector<int> ans;
    
    if (root == NULL) {
        return ans;
    }


    queue<Node*> q;
    q.push(root);
    q.push( NULL );
    ans.push_back( root->data );
    bool flag = true;
    
    while(!q.empty()){
        Node* temp = q.front();
        q.pop();
        if( temp == NULL ){
            if( q.empty() )
                break;
            q.push( NULL );
            flag = true;
        }
        else{
            if( temp->left )
            {
                q.push( temp->left );
                if( flag ){
                    ans.push_back(temp->left->data );
                    flag = 0;
                }
            }
            if( temp->right )
            {
                q.push( temp->right );
                if( flag ){
                    ans.push_back(temp->right->data );
                    flag = 0;
                }
            }
            
        }
        
    }   
    
    return ans;
    
}
```
