```
Input:
BST1:
       5
     /   \
    3     6
   / \
  2   4  
BST2:
        2
      /   \
     1     3
            \
             7
            /
           6
Output: 1 2 2 3 3 4 5 6 6 7
```

```
    void store( vector<int> &vec1 , Node* root1  ){
        if( root1 == NULL )
            return ;
            
        store( vec1 , root1->left );
        vec1.push_back( root1->data );
        store( vec1 , root1->right );
    }
    
    
    
    vector<int> merge(Node *root1, Node *root2)
    {
       vector<int> vec1;
       vector<int> vec2;
       
       store( vec1 , root1 );
       store( vec2 , root2 );
       
       int i=0 ; int j=0;
       vector<int> ans;
       
       while( i < vec1.size() && j<vec2.size() ){
           if( vec1[i] < vec2[j] ){
                ans.push_back( vec1[i] );
                i++;               
           }
           else{
                ans.push_back( vec2[j] );
                j++;   
           }
           
       }
       
       
       while( i < vec1.size() ){
                ans.push_back( vec1[i] );
                i++;  
       }
       
       
       while( j < vec2.size() ){
                ans.push_back( vec2[j] );
                j++;  
       }
       
       return ans;
       
    }
```
