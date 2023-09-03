# Distance from the Source (Bellman-Ford Algorithm)

```
    vector<int> bellman_ford(int V, vector<vector<int>>& edges, int S) {
        vector<int> dis(V , 1e8 );
        dis[S] = 0;
        for( int i=0 ; i<V-1 ; i++ ){
            for( int k=0 ; k<edges.size() ; k++ ){
                int u = edges[k][0];
                int v = edges[k][1];
                int wt = edges[k][2];
                
                if( dis[u] != 1e9 && ((dis[u] + wt) < dis[v]) ){
                    dis[v] = dis[u] + wt;
                }
            }
        }
        
        int flag = 0;
        for( int j=0 ; j<edges.size() ; j++ ){
                int u = edges[j][0];
                int v = edges[j][1];
                int wt = edges[j][2];
                
                if( dis[u] != 1e9 && ((dis[u] + wt) < dis[v]) ){
                    flag = 1;
                }
        }            
        
        
        
        if( flag ){
            return {-1};
        }
        
        return dis;
    
    }
```
