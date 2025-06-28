```
Input: V = 3, edges[][] = [[0, 1, 1], [1, 2, 3], [0, 2, 6]], src = 2
Output: [4, 3, 0]
```

```
    vector<int> dijkstra(int V, vector<vector<int>> &edges, int src) {
        vector<vector<pair<int,int>>> adj( V );
        for( auto& edge : edges ){
            int v = edge[0] ; int u = edge[1] ; int w = edge[2];
            adj[v].push_back( { u , w } );
        }
        
        vector<int> dist( V, 1e9 );
        dist[src] = 0;
        
        priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
        pq.push({0, src});
        
        
        while( !pq.empty() ){
            int d = pq.top().first;
            int u = pq.top().second;
            pq.pop();
            
            if( d > dist[u] ) continue;
            
            for( auto& neigh : adj[u] ){
                int v = neigh.first;
                int w = neigh.second;
                
                if( dist[v] > w + dist[u] ){
                    dist[v] = w + dist[u];
                    pq.push({ dist[v] , v  });
                }
                
            }
            
        }
        
        return dist;

    }
```
