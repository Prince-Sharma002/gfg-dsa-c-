# Topological Sort

```
	
	void solve( int i , vector<bool>& vis , stack<int>& st , vector<int> adj[] ){
	    vis[i] = true;
	    
	    for( auto j : adj[i] ){
	        if( !vis[j] )
	            solve( j , vis , st , adj );
	    }
	    st.push( i );
	    
	    
	}
	
	vector<int> topoSort(int V, vector<int> adj[]) 
	{
	    vector<bool> vis(V , false );
	    stack<int> st;
	    
	    for( int i=0 ; i<V ; i++ ){
	        if( !vis[i] )
	            solve( i , vis , st , adj );
	    }
	    
	    vector<int> ans;
	    while( !st.empty() ){
	        ans.push_back( st.top() );
	        st.pop();
	    }
	    
	    return ans;
	}
```
