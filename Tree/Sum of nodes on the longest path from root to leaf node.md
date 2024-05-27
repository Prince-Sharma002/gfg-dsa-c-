```
Input: 
         4        
       /   \       
      2     5      
     / \   / \     
    7   1 2   3    
       /
      6
Output: 
13
```

```
    void solve( int len , int sum , int& maxSum , int& maxLen , Node* root ){
        
        if( root == NULL ){
            if( len > maxLen ){
                maxLen = len;
                maxSum = sum;
            }
            else if( len == maxLen ){
                maxSum = max(sum , maxSum );
            }
            return ;
        }
        
        sum += root->data;
        solve( len+1 , sum , maxSum , maxLen , root->left );
        solve( len+1 , sum , maxSum , maxLen , root->right );
        
        
    }
    
    int sumOfLongRootToLeafPath(Node *root)
    {
        int len = 0;
        int sum = 0;
        
        int maxSum = INT_MIN ;
        int maxLen = 0 ;
        
        solve( len , sum , maxSum , maxLen , root );
        return maxSum;
    }
```
