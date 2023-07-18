# Diagonal Traversal of Binary Tree

```
vector<int> diagonal(Node *root)
{
   queue<Node*> q;
   Node* temp = root;
   vector<int> ans;
   while( temp ){
       
       ans.push_back( temp->data  );
       
        if( temp->left )
            q.push( temp->left );
        
        if( temp->right )
            temp = temp->right;
        else{
            if( !q.empty() ){
                temp = q.front();
                q.pop();
            }    
            else
                temp = NULL;
        }
        
   }
   return ans;
}
```
