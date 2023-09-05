# Bipartite Graph
```
	bool isBipartite(int V, vector<int>adj[]){
	    queue<pair< int , int >> q;
	    vector<int> vis(V , -1);
	    for( int i=0 ; i<V ; i++  ){
	        if( vis[i] == -1 )
	        {
	        q.push( { i , 0 } );
	        vis[i] = 0;
	        
	        while( !q.empty()) {
	            
	            int node = q.front().first;
	            int col = q.front().second;
	            q.pop();
	            
	            for( auto nbr : adj[node]){
	                if( col == vis[nbr] )
	                    return false;
	                if( vis[nbr] == -1 ){
	                    vis[nbr] = col ? 0 : 1;
	                    q.push({nbr , vis[nbr]});
	                }
	                
	            }
	            
	        }
	        
	        }
	        
	    }
	    
	    return true;
	}
```
