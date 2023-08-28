# Extreme Nodes in alternative order

```
    vector<int> ExtremeNodes(Node* root)
    {
        queue<Node*> q;
        q.push( root );
        vector<int> ans;
        int flag = false;
        while( !q.empty() ){
            int size = q.size();
            int n = size;
            
            while( n-- ){
                
                Node* curr = q.front();
                q.pop();
                
                if( curr->left )
                    q.push( curr->left );
                if( curr->right )
                    q.push( curr->right );
                    
                if( flag && n == size - 1 )
                    ans.push_back( curr->data );
                
                
                if( !flag && n == 0 )
                    ans.push_back( curr->data );
                
                
            }
            
            flag = !flag;
        }
        
        return ans;
    }
```
