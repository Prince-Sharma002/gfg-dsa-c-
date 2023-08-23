# Iterative Preorder Traversal

```
vector<int> preOrder(Node* root)
{
    vector<int> ans;
    stack<Node*> s;
    Node* curr = root;
    while (curr || !s.empty()) {
        while (curr) {
            ans.push_back(curr->data);
            s.push(curr);
            curr = curr->left;
        }
        
        curr = s.top();
        s.pop();
        curr = curr->right; // Move to the right subtree
    }
    
    return ans;
}

```
