```
Input: V = 4, edges[][] = [[0, 1], [0, 2], [1, 2], [2, 0], [2, 3]]
Output: true
Explanation: The diagram clearly shows a cycle 0 → 2 → 0
```

```
bool isCyclic(int V, vector<vector<int>> &edges) {
    vector<vector<int>> adj(V); // ✅ Initialize adj list with V vertices
    vector<int> indegree(V, 0);
    queue<int> q;

    // Create adj list
    for (auto edge : edges) {
        adj[edge[0]].push_back(edge[1]);
    }

    // Calculate indegree
    for (int i = 0; i < V; i++) {
        for (auto j : adj[i]) {
            indegree[j]++;
        }
    }

    // Push nodes with 0 indegree
    for (int i = 0; i < V; i++) {
        if (indegree[i] == 0)
            q.push(i);
    }

    int count = 0;
    while (!q.empty()) {
        int node = q.front();
        q.pop();
        count++;

        for (auto j : adj[node]) {
            indegree[j]--;
            if (indegree[j] == 0)
                q.push(j);
        }
    }

    // ✅ Return true if cycle exists (i.e., not all nodes processed)
    if (count == V)
        return false; // No cycle
    return true;     // Cycle exists
}
```
