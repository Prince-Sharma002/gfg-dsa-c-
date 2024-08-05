```
vector<int> bottomView(Node *root) {
    vector<int> ans;
    if (!root) return ans; // Add a check for an empty tree

    int hd = 0;
    queue<pair<Node*, int>> q;
    map<int, int> mp; // Use a map instead of unordered_map to maintain order of horizontal distance keys

    q.push({root, 0});

    while (!q.empty()) {
        Node* node = q.front().first;
        int dis = q.front().second;
        q.pop();

        // Update the map with the bottom-most node at the current horizontal distance
        mp[dis] = node->data;

        if (node->left)
            q.push({node->left, dis - 1}); // Use dis - 1 for the left child

        if (node->right)
            q.push({node->right, dis + 1}); // Use dis + 1 for the right child
    }

    for (auto i : mp) {
        ans.push_back(i.second);
    }

    return ans;
}

```
