# Construct Tree from Inorder and Preorer

```
int search(int in[], int key, int s, int e) {
    for (int i = s; i <= e; i++) {
        if (in[i] == key)
            return i;
    }
    return -1;
}

Node* build(int in[], int pre[], int instrt, int inend) {
    static int preIndex = 0;

    if (instrt > inend)
        return nullptr;

    Node* node = new Node(pre[preIndex++]);

    if (instrt == inend)
        return node;

    int ind = search(in, node->data, instrt, inend);

    node->left = build(in, pre, instrt, ind - 1);
    node->right = build(in, pre, ind + 1, inend);

    return node;
}

Node* buildTree(int in[], int pre[], int n) {
    return build(in, pre, 0, n - 1);
}
```
