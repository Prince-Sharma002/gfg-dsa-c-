# Articulation Point - I

```
  void dfs( int node , int parent , int& timer , vector<int>& dis , vector<int>& low ,
            vector<bool>& vis , vector<int> adj[] , vector<bool>& ap ){
        
            vis[node] = true;
            dis[node] = low[node] = timer++;
            int child = 0;
            for( auto nbr : adj[node] ){
                if( parent == nbr )
                    continue;
                if( !vis[nbr] ){
                    dfs(nbr , node , timer , dis , low , vis , adj , ap );
                    low[node] = min( low[node] , low[nbr] );
                    if( low[nbr] >= dis[node] && parent != -1  ){
                        ap[node] = true;
                    }
                    child++;
                }
                else{
                    low[node] = min( low[node] , dis[nbr] );
                }
                
            }
            
            if( parent == -1   && child > 1){
                ap[node] = true;
            }
                
    }
  
  
    vector<int> articulationPoints(int V, vector<int>adj[]) {
        int parent = -1;
        int timer =  0;
        vector<int> dis(V , -1);
        vector<int> low(V , -1);
        vector<bool> vis(V, false);
        
        vector<int> ans;
        vector<bool> ap(V, false);
        for( int i=0 ; i<V ; i++ ){
            if( !vis[i] )
                dfs( i , parent , timer , dis , low , vis , adj , ap);
        }
        for( int i=0 ; i<V ; i++ ){
            if( ap[i] == true)
                ans.push_back(i);
        }
        if( ans.size() == 0 ){
            ans.push_back( -1);
        }
        return ans;
    }
```
