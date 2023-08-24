# construct Binary Tree from array

```
Node* createTree(int parent[], int N)
{
    vector<Node*> nodes(N); // Array to hold node pointers
    for (int i = 0; i < N; i++) {
        nodes[i] = new Node(i);
    }

    Node* root = nullptr;
    for (int i = 0; i < N; i++) {
        if (parent[i] == -1) {
            root = nodes[i];
        } else {
            
            // nodes[parent[i]] gives nodes of value parent[i]  
            if (nodes[parent[i]]->left == nullptr) {
                nodes[parent[i]]->left = nodes[i];
            } else {
                nodes[parent[i]]->right = nodes[i];
            }
        }
    }

    return root;
}
```
