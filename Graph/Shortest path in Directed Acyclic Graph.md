# Shortest path in Directed Acyclic Graph

```
      void findTopoSort(int node, int vis[], stack<int> &st, vector<pair<int, int>> adj[]) {
        vis[node] = 1;
        for (auto it : adj[node]) {
            if (!vis[it.first]) {
                findTopoSort(it.first, vis, st, adj);
            }
        }
        st.push(node);
    }
  
  
  
     vector<int> shortestPath(int N,int M, vector<vector<int>>& edges){
        vector< pair<int,int>> adj[N];
        int src = 0;
        
        for( int i=0 ; i<M ; i++ ){
            adj[edges[i][0]].push_back( {edges[i][1] , edges[i][2]} );
        }
        
        
        int vis[N] = { 0 };
        stack<int> st;
        
        
        for( int i=0 ; i<N ; i++ ){
            if( !vis[i] )
                findTopoSort(i, vis, st, adj);
        }
        
        vector<int> dis( N , 1e9 );
        dis[src] = 0;
        
        while( !st.empty() ){
            int node = st.top();
            st.pop();
            
            if( dis[node] != 1e9 ){
                for( auto i : adj[node] ){
                    
                    // dis[node] - currnode distance 
                    // i.second - distance between node and i node
                    // i.first - adjacent list connected node to currNode
                    if( dis[node] + i.second < dis[i.first]  )
                        dis[i.first] = dis[node] + i.second;
                }
            }
            
        }
        
        
        for (int i = 0; i < dis.size(); ++i) {
            if (dis[i] ==  1e9) dis[i] = -1;
        }

        // Returning the shortest path array
        return dis;
        
    }
```
