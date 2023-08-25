
# preOrder to PostOrder

```
    //Function that constructs BST from its preorder traversal.
 Node* post_order(int pre[], int size) {
    if (size == 0) {
        return nullptr;  // Handle the case of an empty array
    }

    stack<Node*> s;
    Node* root = newNode(pre[0]);
    s.push(root);

    for (int i = 1; i < size; i++) {
        Node* temp = nullptr;
        
        while( !s.empty() && s.top()->data < pre[i]  ){
            temp = s.top();
            s.pop();
        }
        
        if( temp ){
            temp->right = newNode( pre[i] );
            s.push( temp->right );
        }
        else{
            s.top()->left = newNode( pre[i] );
            s.push( s.top()->left );
        }
        
    }

    return root;
}
```
