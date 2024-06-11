```
Input:
6
1 7 5 50 40 10

Output:
1 5 7 10 40 50
```

```
Node* solve( int post[] , int mini , int maxi , int* postInd , int key  ){
    if( *postInd < 0 )
        return NULL;
    
    
    Node* node = NULL;
    if( key > mini &&  key < maxi ){
        
        node = new Node( key );    
        *postInd = *postInd - 1;
         
        if( postInd >= 0)
        {
            node->right = solve( post , key , maxi , postInd , post[ *postInd ] );
            node->left = solve( post , mini, key , postInd , post[ *postInd ] );
        }
        
    }
    return node;
    
    
}

Node *constructTree (int post[], int size)
{
    int postInd = size-1;
    
    return solve( post , INT_MIN , INT_MAX , &postInd , post[ postInd ] );
}
```
