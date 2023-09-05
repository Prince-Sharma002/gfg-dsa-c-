# Level of node in graph

```
	struct bfsStruct{
	    public :
	    int count ;
	    int node ;
	    bfsStruct( int count , int node ){
	        this->count = count ;
	        this->node = node;
	    }
	};
	
	
	int nodeLevel(int V, vector<int> adj[], int X) 
	{
	    queue<bfsStruct> q;
	    q.push(bfsStruct(0 , 0));
	    
	    vector<bool> vis(V , false);
	    while( !q.empty() ){
	        bfsStruct node = q.front();
	        int count = node.count;
	        int data = node.node;
	        
	        q.pop();
	        
	        if( data == X )
	            return count;
	        
	        vis[data] = true;
	        
	        for( auto j : adj[data]){
	            if( !vis[j] ){
	                q.push( bfsStruct( count+1 , j ) );    
	            }
	            
	        }
	        
	    }
	    
	    return -1;
	    
	}
```
