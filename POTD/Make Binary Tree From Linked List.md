```
Input: list = 1->2->3->4->5
Output: 1 2 3 4 5
Explanation: The tree would look like
      1
    /   \
   2     3
 /  \
4   5
Now, the level order traversal of
the above tree is 1 2 3 4 5.
```

```
    TreeNode* constructTree( int i , int n , vector<int>& arr ){
        if( i >= n )
            return NULL;
        
        TreeNode* node = new TreeNode(arr[i]);
        node->left = constructTree( 2*i + 1 , n  , arr );
        node->right = constructTree( 2*i + 2 , n  , arr );
        
        return node;
        
    }
    
    
    void convert(Node *head, TreeNode *&root) {
        vector<int> arr;
        Node* temp = head;
        while( temp ){
            arr.push_back( temp->data ); 
            temp = temp->next;
        }
        
        int n = arr.size();
        
        root = constructTree( 0 , n  , arr );
    }
```
