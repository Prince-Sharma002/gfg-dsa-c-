# Largest BST

```
struct info {
    int size;
    int min;
    int max;
    int ans;
    bool isbst;
};

info solve(Node* root) {
    if (!root)
        return {0, INT_MAX, INT_MIN, 0, true};  // Update min and max

    if (!root->left && !root->right)
        return {1, root->data, root->data, 1, true};

    info l = solve(root->left);
    info r = solve(root->right);

    info ret;
    ret.size = 1 + l.size + r.size;

    // Check for whole bst
    if (l.isbst && r.isbst && root->data > l.max && root->data < r.min) {
        ret.min = min(l.min, root->data);
        ret.max = max(r.max, root->data);

        ret.ans = l.ans + r.ans + 1;
        ret.isbst = true;

        return ret;
    }

    // If it's not a valid BST
    ret.ans = max(l.ans, r.ans);
    ret.isbst = false;
    return ret;
}

int largestBst(Node* root) {
    return solve(root).ans;
}

```
