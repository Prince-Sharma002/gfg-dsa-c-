```
Input:
        2
      /   \
     1     3
sum = 5
Output: 1 
```

```
    void solve( struct Node* root , vector<int> &arr ){
        if( !root )
            return ;
        
        solve( root->left , arr );
        arr.push_back( root->data );
        solve( root->right , arr);
        
    }
    
    int isPairPresent(struct Node *root, int target)
    {
        vector<int> arr;
        solve( root , arr);
        
        int i=0 ;
        int j = arr.size()-1;
        while( i < j ){
            if( arr[i] + arr[j] == target )
                return 1;
            else if( arr[i] + arr[j] > target  )
                j--;
            else 
                i++;
        }
        
        return 0;
        
    }
```
