# BFS OF GRAPH

```
    vector<int> bfsOfGraph(int V, vector<int> adj[]) {
        vector<bool> vis(V , false );
        int s = 0;
        vis[s] = true;
        
        queue<int> q;
        q.push( s );
        
        vector<int> ans;
        
        while( !q.empty() ){
         int t = q.front();
         ans.push_back(t);
         q.pop();
         
         for( int i : adj[t] ){
             if( !vis[i] ){
                 vis[i]  = true;
                 q.push( i );
             }
         }
            
        }
        
        return ans;
    }
```
