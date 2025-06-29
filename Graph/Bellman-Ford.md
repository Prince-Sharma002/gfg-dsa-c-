```
Input: V = 5, edges[][] = [[1, 3, 2], [4, 3, -1], [2, 4, 1], [1, 2, 1], [0, 1, 5]], src = 0
Output: [0, 5, 6, 6, 7]
```

```
    vector<int> bellmanFord(int V, vector<vector<int>>& edges, int src) {
        vector<int> dist( V, 1e9 );
        dist[src] = 0;
        
        int m = edges.size();
        for( int i=1 ; i<= V-1 ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                int u = edges[j][0];
                int v = edges[j][1];
                int w = edges[j][2];
                
                if( dist[v] > dist[u] + w )
                    dist[v] = dist[u] + w;
            }
        }
        
        bool flag = false;
        for( int i=1 ; i<= V-1 ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                int u = edges[j][0];
                int v = edges[j][1];
                int w = edges[j][2];
                
                if( dist[v] > dist[u] + w )
                    flag = true;
            }
        }
        
        if( flag ) return {-1};
        return dist;
        
    }
```
