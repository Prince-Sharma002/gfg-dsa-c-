# Strongly Connected Components (Kosaraju's Algo)

```
    void dfs( int node , vector<bool>& vis , vector<vector<int>> adj , stack<int>& st ){
        vis[node] = true;
        
        for( auto nbr : adj[node] ){
            if(!vis[nbr])
                dfs( nbr , vis , adj , st );
        }
        
        st.push( node );
    }
    
    void revdfs( int node , vector<bool>& vis , vector<int> tran  ){
        vis[node] = true;
        
        for( auto nbr : tran[node] ){
            if(!vis[nbr])
                revdfs( nbr , vis , tran  );
        }
        
        
    }    
    
    
    int kosaraju(int V, vector<vector<int>>& adj)
    {
        vector<bool> vis( V , false );
        stack<int> st;
        
        for( int i=0 ; i<V ; i++ ){
            if( !vis[i] )
                dfs( i , vis , adj , st );
        }
        
        // transpose of graph
        vector<int> tran[V];
        for( int i=0 ; i<V ; i++ ){
            vis[i] = false;
            for(  auto nbr : adj[i] ){
                tran[nbr].push_back(i);
            }
        }
        
        int count = 0;
        while( !st.empty() ){
            int Node = st.top();
            st.pop();
            if( !vis[Node] ){
                revdfs( Node , vis , tran );
                count++;
            }
        }
        
        return count;
        
    }
```
