```
Input: tree = 1,  target = 4
            /   \
          2     3
Output: true
```

```
    bool solve( Node* root , int target , int sum ){
        if( root == NULL )
            return false;
        sum += root->data;
        
        if( root->left == NULL && root->right == NULL )
            return sum == target;
 
        return solve( root->left , target , sum ) || solve( root->right , target , sum );
 
    }
    bool hasPathSum(Node *root, int target) {
        int sum = 0;
        return solve( root , target , sum );
    }
```
