```
Input: 
Tree = 
           1
        /     \
      3        -1
    /   \     /   \
   2     1   4     5                        
        /   / \     \                    
       1   1   2     6    
K = 5                    
Output: 
8
```

```
  void solve( Node* root , int k , vector<int> &path , int &ans ){
      if( root == NULL )
        return ;
    
      path.push_back( root->data );
      int size = path.size();
      
      solve( root->left , k , path , ans );
      solve( root->right , k , path , ans );
      
      int sum = 0;
      for( int i = size-1 ; i >= 0 ; i-- ){
          sum += path[i];
          if( sum == k )
            ans++;
      }
      
      path.pop_back();
        
  }
  
    int sumK(Node *root,int k)
    {
        vector<int> path;
        int ans = 0;
        solve( root , k , path , ans );
        return ans;
    }
```
