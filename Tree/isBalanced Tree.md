# isBalanced Tree

```
    int height( Node* root ){
        if( !root )
            return 0;
        
        return max( height(root->left) , height(root->right) ) + 1;
    }
    bool isBalanced(Node *root)
    {
        if( root == NULL )
            return true;
        int lh = height(root->left);
        int rh = height(root->right);
        
        if( abs(lh -rh ) <= 1 && isBalanced(root->left) && isBalanced(root->right ) )
            return true;
        return false;
    }
```
```
    pair<bool , int> solve( Node* root ){
        if( root == NULL)
        {
            pair<bool , int > p = make_pair( true , 0 );
            return p;
        }
        
        pair< bool , int> left = solve( root->left );
        pair< bool , int> right = solve( root->right );
        
        bool leftAns = left.first;
        bool rightAns = right.first;
        
        
        bool diff = abs( left.second - right.second ) <= 1 ; 
        
        pair<bool , int> ans;
        if( leftAns && rightAns && diff)    
        {
            ans.first = true;
            ans.second = max( left.second , right.second ) + 1;
           
        }
        else{
            ans.first = false;
        }
        
        return ans;
        
        
    }
    
    
    bool isBalanced(Node *root)
    {
        return solve( root).first;
    }
```
