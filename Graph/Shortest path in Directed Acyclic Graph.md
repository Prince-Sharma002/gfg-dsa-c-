# Shortest path in Directed Acyclic Graph

```
  void topoSort( int i , vector<bool>& vis , vector<pair<int,int>> adj[] , stack<int>& st ){
      
      vis[i] = true;
      for( auto j : adj[i] ){
          if( !vis[j.first] ){
              topoSort( j.first , vis , adj , st );
          }
      } 
      
      st.push( i );
      
  }
  
     vector<int> shortestPath(int N,int M, vector<vector<int>>& edges){
        
        vector<pair<int,int>> adj[N];
        int src = 0 ;
        
        for( int i=0 ; i<M ; i++ ){
            adj[ edges[i][0] ].push_back( {edges[i][1] , edges[i][2]} );
        }
        
        vector<bool> vis(N , false);
        stack<int> st;
        for( int i=0 ; i<N ; i++ ){
            if( !vis[i] )
                topoSort( i , vis , adj , st);
        }
        
        
        vector<int> dist( N , 1e9 );
        dist[src] = 0;
        
        while( !st.empty() ){
            int node = st.top();
            st.pop();
            
            if( dist[node] != 1e9 ){
                for( auto i : adj[node] ){
                    if( dist[node] + i.second < dist[i.first] )
                        dist[i.first] = dist[node] + i.second;
                }
            }
        }
        
        
        for (int i = 0; i < dist.size(); ++i) {
            if (dist[i] ==  1e9) dist[i] = -1;
        }

        // Returning the shortest path array
        return dist;
    }
```
