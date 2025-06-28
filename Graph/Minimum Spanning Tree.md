```
    int spanningTree(int V, vector<vector<int>> adj[]) {
        vector<bool> mst( V , false );
        priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;

        pq.push({ 0 , 0 });
        int totalweight = 0;
        
        while( !pq.empty() ){
            
            int w = pq.top().first;
            int u = pq.top().second;
            pq.pop();
            
            if( mst[u] ) continue;
            
            totalweight += w;
            mst[u] = true;
            
            for( auto& edge : adj[u] ){
                int v = edge[0];
                int weight = edge[1];
                
                if( !mst[v] )
                    pq.push({ weight, v });
                
            }
            
            
        }
        
        return totalweight;
        
        
        
    }
```
