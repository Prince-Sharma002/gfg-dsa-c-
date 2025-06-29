```
    
static bool cmp(vector<int>& a, vector<int>& b) {
    return (a[2] < b[2]);
}

int findparent(int node, vector<int>& parent) {
    if (parent[node] == node)
        return node;
    return parent[node] = findparent(parent[node], parent);
}

void makeset(vector<int>& parent, vector<int>& rank, int n) {
    for (int i = 0; i < n; i++) {
        parent[i] = i;
        rank[i] = 0;
    }
}

void unionSet(int u, int v, vector<int>& parent, vector<int>& rank) {
    u = findparent(u, parent);
    v = findparent(v, parent);

    if (rank[u] > rank[v])
        parent[v] = u;
    else if (rank[u] < rank[v])
        parent[u] = v;
    else {
        parent[u] = v;
        rank[v]++;
    }
}

int spanningTree(int V, vector<vector<int>>& edges) {
    sort(edges.begin(), edges.end(), cmp);

    vector<int> parent(V);
    vector<int> rank(V);
    makeset(parent, rank, V);

    int totalweight = 0;

    for (int i = 0; i < edges.size(); i++) {
        int u = findparent(edges[i][0], parent);
        int v = findparent(edges[i][1], parent);
        int weight = edges[i][2];

        if (u != v) {
            unionSet(u, v, parent, rank);
            totalweight += weight;
        }
    }

    return totalweight;
}
```
