# Cycle detection in graph

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
