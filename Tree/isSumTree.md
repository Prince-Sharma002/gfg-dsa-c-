```
Input:

          10
        /    \
      20      30
    /   \ 
   10    10

Output: 0
```

```
    pair< bool , int > solve( Node* root ){
        
        if( root == NULL )
        {
            pair<bool , int> p = make_pair(true , 0 );
            return p;            
        }
        
        if( root->left == NULL && root->right == NULL )
        {
            pair<bool , int> p = make_pair(true , root->data );
            return p;
        }
        
        
        pair<bool , int> left = solve( root->left );
        pair<bool , int> right = solve( root->right );
        
        
        pair<bool , int> ans;
        int sum = left.second + right.second;
        if( left.first && right.first &&  sum == root->data )
        {
            ans.first = true;
            ans.second = sum + root->data;
        }
        else
        {
            ans.first = false;
        }
        return ans;
        
        
    }
    
    bool isSumTree(Node* root)
    {
        return solve( root ).first;
    }

```
