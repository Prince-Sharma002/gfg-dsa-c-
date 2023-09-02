# Bridge edge in a graph

```
    void dfs( int i , vector<int> adj[] , vector<bool>& vis ){
        vis[i] = true;
        
        for( auto j : adj[i] ){
            if(!vis[j] )
                dfs( j , adj , vis );
        }
        
    }
    
    
    bool isConnected( int V , vector<int> adj[] , int c , int d ){
        vector<bool> vis(V , false);
        

        dfs( c , adj , vis);
        
        if( vis[d] == false )
            return false;
        return true;
        
    }
    
    int isBridge(int V, vector<int> adj[], int c, int d) 
    {
        if( !isConnected( V ,  adj , c , d ) )
            return false;
            
            
            adj[c].erase(remove(adj[c].begin(), adj[c].end(), d), adj[c].end());
            adj[d].erase(remove(adj[d].begin(), adj[d].end(), c), adj[d].end());
            
            //if graph is connected, we return false else true.
            if (isConnected(V ,  adj , c , d))
                return 0;
            else
                return 1;
    }
```
