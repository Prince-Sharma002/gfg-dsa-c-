# Possible paths between 2 vertices

```
    void solve( int& count , int src, int dest , vector<int> adj[] , vector<bool>& vis ){
        vis[src] = true;
        
        if( src == dest )
            count += 1;
        
        for( auto j: adj[src] ){
            if( !vis[j] ){
                solve( count , j , dest , adj , vis );        
            }
        }
        
        vis[src] = false;
    }
    
    int countPaths(int V, vector<int> adj[], int source, int destination) {
        vector<bool> vis(V , false);
        int count  = 0;
        solve( count , source , destination , adj , vis );
        
        return count;
    }
```
