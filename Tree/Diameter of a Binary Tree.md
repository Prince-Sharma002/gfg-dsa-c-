```
Input:
         10
        /   \
      20    30
    /   \ 
   40   60
Output: 4
```


```

pair<int , int> fastDiameter( Node* root ){
    
    if( root == NULL ){
        pair<int , int> p = make_pair(0 , 0);
        return p;
    }
     
    pair<int , int> left = fastDiameter( root->left );
    pair<int , int> right = fastDiameter( root->right );
    
    int op1 = left.first;
    int op2 = right.first;
    int mixed = left.second + right.second + 1;
    
    pair<int , int> ans;
    ans.first = max( op1, max( op2 , mixed ) );
    ans.second = max( left.second , right.second ) + 1;
        
    return ans;

    
}


int diameter(Node* root) {
        
    if(root == NULL)
        return 0;
            
    return fastDiameter(root).first;        
    
        
}
```
