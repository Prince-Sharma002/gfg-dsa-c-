# Preorder Traversal and BST

```
    int canRepresentBST(int arr[], int N) {
        
        int root = INT_MIN;
        stack<int> s;
        
        for( int i=0 ; i<N ; i++ ){
            
            // if root's right element is lesser return false
            if( arr[i] < root )
                return 0;
            
            // curr element is greater than s.top pop to find root element
            while( !s.empty() && s.top() < arr[i] ){
                root = s.top();
                s.pop();
            }
            
            s.push( arr[i] );
            
        }
        
        return 1;
        
    }
```
