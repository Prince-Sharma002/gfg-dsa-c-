# Reverse Level Order Traversal
```
vector<int> reverseLevelOrder(Node *root)
{
    vector<int> ans;
    queue<Node*> q;
    q.push( root );
    while( !q.empty() ){
        Node* temp = q.front();
        ans.push_back(temp->data);
        q.pop();
        if( temp->right ) q.push( temp->right );
        if( temp->left ) q.push( temp->left );
    }
    
    int i=0 ; int j=ans.size() - 1;
    while( i < j ){
        swap( ans[i] , ans[j] );
        i++; j--;
    }
    
    return ans;
}
```
