```
Input:
      1
   /    \
  2      3
Output: 2 1 3
```

```
    vector<int> topView(Node *root)
    {
        vector<int> ans;
        if( root == NULL )
            return ans;
        
        map< int , int  > mp;
        queue< pair<int , Node*> > q;
        q.push({ 0 , root });
        
        while( !q.empty() ){
            
            pair< int , Node* > temp = q.front();
            int hd = temp.first;
            Node* node = temp.second;
            q.pop();
            
            if( mp.find(hd) == mp.end() )
                mp[hd] = node->data;
            
            if( node->left )
                q.push( { hd-1 , node->left } );
            if( node->right )
                q.push( { hd+1 , node->right } );
                
        }
        
        for( auto it = mp.begin() ; it != mp.end() ; it++ ){
            ans.push_back( it->second );
        }
        
        return ans;
        
    }
```
