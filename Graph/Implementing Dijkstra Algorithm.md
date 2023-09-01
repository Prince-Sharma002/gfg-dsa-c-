# Implementing Dijkstra Algorithm

```
    vector <int> dijkstra(int V, vector<vector<int>> adj[], int S)
    {
        vector<int> dist( V , 1e9 );
        set<pair<int,int>> st;
        dist[S] = 0;
        st.insert( {0,S});
        
        while( !st.empty() ){
            auto top = *( st.begin() );
            
            int nodeDist = top.first;
            int topNode = top.second;
            
            st.erase( st.begin() );
            for( auto i : adj[topNode]){
                if( nodeDist + i[1] < dist[i[0]] ){
                    auto record = st.find( {dist[i[0]] ,i[0]} );
                
                    if( record != st.end() )
                        st.erase(record);
                    
                    dist[i[0]] = nodeDist + i[1];
                    st.insert( {dist[i[0]] , i[0]});
                }
                
                
            }
        }
        
        return dist;
    }
```
