# Prereuisite Task

```
    bool isCycle( int node , vector<bool>& vis , vector<bool>& dfsvis , vector<vector<int>>& adj ){
        
        vis[node] = true;
        dfsvis[node] = true;
        for( auto nbr : adj[node] ){
            if( !vis[nbr]){
                bool check = isCycle( nbr , vis , dfsvis , adj );
                if( check )
                    return true;
            }
            else if( dfsvis[nbr] )
                    return true;
        }
        
        dfsvis[node] = false;
        return false;
        
    }


	bool isPossible(int N,int P, vector<pair<int, int> >& prerequisites) {
	    vector<vector<int>> adj(N);
	    for( int i=0 ; i<P ; i++ ){
	        int u = prerequisites[i].first;
	        int v = prerequisites[i].second;
	        
	        adj[v].push_back( u );
	    }
	    
	    vector<bool> vis( N , false );
	    vector<bool> dfsvis( N , false );
	    
        for( int i=0 ; i<N ; i++ ){
            if( !vis[i] )
                if( isCycle( i , vis ,  dfsvis ,adj  ) ) return false;
        }
	    
	    return true;
	}
```
