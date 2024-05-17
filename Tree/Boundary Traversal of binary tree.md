```
Input:
        1 
      /   \
     2     3  
    / \   / \ 
   4   5 6   7
      / \
     8   9
   
Output: 1 2 4 8 9 6 7 3
```

```
    void leftTraversal( Node* root , vector<int> &ans ){
        if( root == NULL || ( root->left == NULL && root->right == NULL ))
            return ;
        
        ans.push_back( root->data );
        if( root->left )
            leftTraversal(root->left , ans);
        else if( root->right )
            leftTraversal(root->right , ans);
    }
    
    void leafTraversal( Node* root , vector<int> &ans ){
        if( root == NULL )
            return ;
        
        if( ( root->left == NULL && root->right == NULL )){
            ans.push_back( root->data  );
            return ;
        }
        

        leafTraversal( root->left , ans );
        leafTraversal( root->right , ans);
        
    }
    
    void rightTraversal( Node* root , vector<int> &ans ){
        if( root == NULL || ( root->left == NULL && root->right == NULL ))
            return ;
        
        if( root->right )
            rightTraversal(root->right , ans);
        else if( root->left )
            rightTraversal(root->left , ans);
        ans.push_back( root->data );
    }


    vector <int> boundary(Node *root)
    {
        vector<int> ans;
        if( root == NULL )
            return ans;
            
        ans.push_back( root->data );
        leftTraversal( root->left, ans );
        leafTraversal( root ->left , ans);
        leafTraversal( root ->right , ans);
        rightTraversal(root->right , ans);
        
        
        return ans;
    }
```
