# Bridges In A Graph

```
void dfs( int i , int parent , int& timer , vector<int>& dis , vector<int>& low 
        , vector<vector<int>>& res , unordered_map<int , list<int>> adj , 
        unordered_map< int , bool >& vis ){

        vis[i] = true;
        dis[i] = low[i] = timer++;

        for( auto nbr : adj[i] ){
            if( nbr == parent )
                continue;
            if( !vis[nbr] ){
                dfs( nbr , i , timer , dis , low , res , adj , vis );
                low[i] = min( low[i] , low[nbr] );
                if( low[nbr] > dis[i]){
                    vector<int> ans;
                    ans.push_back( i );
                    ans.push_back( nbr );
                    res.push_back( ans );
                }
            }
            else{
                low[i] = min( low[i] , dis[nbr] );
            }
        }

}




vector<vector<int>> findBridges(vector<vector<int>> &edges, int v, int e) {
    unordered_map<int , list<int>> adj;
    for( int i=0 ; i<edges.size() ; i++ ){
        int u = edges[i][0];
        int v = edges[i][1];

        adj[u].push_back(v);
        adj[v].push_back(u);
    }

    int timer = 0;
    vector<int> dis(v);
    vector<int> low(v);
    int parent = -1;
    unordered_map< int , bool > vis;

    for( int i=0 ; i<v ; i++ ){
        dis[i] = -1;
        low[i] = -1;
    }


    vector<vector<int>> res;
    for( int i=0 ; i<v ; i++ ){
        if( !vis[i] )
            dfs( i , parent , timer , dis , low , res , adj , vis);
    }

    return res;

}
```
