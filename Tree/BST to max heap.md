# BST to max heap

```
 void maxHeapify(Node* root) {
    if (!root)
        return;

    Node* largest = root;
    Node* left = root->left;
    Node* right = root->right;

    if (left != nullptr && left->data > largest->data)
        largest = left;
    if (right != nullptr && right->data > largest->data)
        largest = right;

    if (largest != root) {
        swap(root->data, largest->data);
        maxHeapify(largest);
    }
}

void inorder(Node* root, vector<int>& ans) {
    if (!root)
        return;

    inorder(root->left, ans);
    ans.push_back(root->data);
    inorder(root->right, ans);
}

void modify(Node* root, vector<int>& ans  , int* i) {
    if (!root)
        return;
    

    modify(root->left, ans , i );
    modify(root->right, ans , i );
    root->data = ans[++*i];
}

void convertToMaxHeapUtil(Node* root) {
    vector<int> ans;
    inorder(root, ans);
    
    int i = -1;
    modify(root, ans , &i);
    maxHeapify(root);
}
```
