# Course Schedule

```
#include <vector>
#include <queue>

vector<int> findOrder(int n, int m, vector<vector<int>>& prerequisites) {
    vector<int> ans;
    vector<vector<int>> adj(n);
    vector<int> inDegree(n, 0);

    for (int i = 0; i < m; i++) {
        int u = prerequisites[i][0];
        int v = prerequisites[i][1];

        adj[v].push_back(u);
        inDegree[u]++;
    }

    queue<int> q;
    for (int i = 0; i < n; i++) {
        if (inDegree[i] == 0) {
            q.push(i);
        }
    }

    while (!q.empty()) {
        int node = q.front();
        q.pop();
        ans.push_back(node);

        for (int nbr : adj[node]) {
            inDegree[nbr]--;
            if (inDegree[nbr] == 0) {
                q.push(nbr);
            }
        }
    }

    if (ans.size() != n) {
        // There is a cycle, return an empty vector to indicate impossibility.
        return {};
    }

    return ans;
}

```
