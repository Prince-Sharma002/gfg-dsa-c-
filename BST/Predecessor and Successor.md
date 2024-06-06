```
Input:
      8
    /   \
   1     9
    \     \
     4    10
    /
   3
key = 8 Output: 
4 9
```


```
void solve(Node* root, std::vector<Node*>& in) {
    if (!root) return;

    solve(root->left, in);
    in.push_back(root);
    solve(root->right, in);
}

void findPreSuc(Node* root, Node*& pre, Node*& suc, int key) {
    std::vector<Node*> in;
    solve(root, in);

    pre = nullptr;
    suc = nullptr;


    // if key is found
    for (int i = 0; i < in.size(); i++) {
        Node* temp = in[i];
        int data = temp->key;

        if (data == key) {
            if (i > 0) pre = in[i - 1];
            if (i < in.size() - 1) suc = in[i + 1];
            return;
        }
        
    }
    
    int i ;
    
    // if not found then print first element greater than key as successor and then pred is i-1
    for ( i = 0; i < in.size(); i++) {
        Node* temp = in[i];
        int data = temp->key;

      

        if (data > key) {
            if (i > 0) pre = in[i - 1];
            if (i < in.size() ) suc = in[i];
            return;
        }
        
    }
    
    // check if key is greater then maximum element of tree
    if (i > 0) pre = in[i - 1];
     
    
    return;
    
}
```
