# DFS of Graph

```
    void dfs( int i , vector<bool>& vis , vector<int> adj[] , vector<int>& ans )
    {
        if( vis[i] )
            return ;
        
        // make nodes vis true and store in ans
        vis[i] = true;
        ans.push_back( i );    
            
            
        for( int j : adj[i] ){
            if( !vis[j] ){
                dfs( j , vis , adj , ans );
            }
        }
        
    }
    
    vector<int> dfsOfGraph(int V, vector<int> adj[]) {
        vector<bool> vis(V, false);
        vector<int> ans;
        
        
        for( int i=0 ; i<V ; i++ ){
            if( !vis[i] )
                dfs( i , vis , adj , ans );
        }
        
        return ans;
        
    }
```
