```
Input:
       30
      /
     20
    /
   10
Output:
     20
   /   \
 10     30
```

```
    
    void storebst( Node* root , vector<int>& in  ){
        
        if( root == NULL )
            return ;
        
        storebst( root->left , in ); 
        in.push_back( root->data );
        storebst( root->right , in );        
        
        
    }
    
    
    Node* convertToBst( vector<int> &in , int s , int e ){
        if( s > e) 
            return NULL;
            
        int mid = ( s + e )/2;
        
        Node* node = new Node( in[mid] );
        
        node->left = convertToBst(  in  , s , mid -1  );
        node->right = convertToBst(  in  , mid+1 , e );
        
        return node;
        
    }
    
    
    
    Node* buildBalancedTree(Node* root)
    {
    	vector<int> in;
    	
    	storebst( root , in );
    	
    	int s = 0; int e = in.size() - 1;
    	return convertToBst( in  , s , e );
    }
```
