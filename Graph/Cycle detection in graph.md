# Cycle detection in graph


### using BFS
```
bool isCycle(int V, vector<int> adj[]) {
    map<int, int> parent;
    queue<int> q;
    
    vector<bool> vis(V, false);
    q.push(0);
    vis[0] = true;
    parent[0] = -1;
    
    while (!q.empty()) {
        int t = q.front();
        q.pop();
        
        for (auto i : adj[t]) {
            if (vis[i] && i != parent[t]) {
                return true;
            } else if (!vis[i]) {
                vis[i] = true;
                q.push(i);
                parent[i] = t;
            }
        }
    }
   
    return false;
}
```


### using DFS
```

bool detect( int i , vector<int> adj[] , int parent , vector<bool> vis )
{
    vis[i] = true;
    
    for( auto j : adj[i] ){
        if( !vis[j] ){
            return detect( j , adj , i , vis );
        }
        else if( parent != j )
            return true;
    }
    return false;
}

bool isCycle(int V, vector<int> adj[]) {
    vector<bool> vis(V , false);
    
    int parent = -1;
    for( int i=0 ; i<V ; i++ ){
        if( !vis[i] ){
            if( detect( i , adj , parent , vis) ) return true;
        }
    }
   
    return false;
}
```

