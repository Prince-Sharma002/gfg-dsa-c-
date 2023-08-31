# Cycle Detection in Directed Graph
```
    bool solve( int i , map<int , bool >& vis , map<int , bool >& dfsVis , vector<int> adj[] )
    {
        vis[i] = true;
        dfsVis[i] = true;
        
        for( auto j : adj[i] ){
            if( !vis[j] ){
                bool cycleDetected =  solve( j , vis , dfsVis , adj );
                if( cycleDetected )
                    return true;
            }
            else if( dfsVis[j] )
                return true;
        }
        dfsVis[i] = false;
        return false;
    }
    
    
    bool isCyclic(int V, vector<int> adj[]) {
        map<int , bool> vis;
        map<int , bool> dfsVis;
    
        
        for( int i=0 ; i<V ; i++ ){
            if( !vis[i] )
                if( solve( i , vis ,  dfsVis ,adj  ) ) return true;
        }
        return false;
    }
```
