```
Input: k=1, mat=[[1,2,3],[4,5,6],[7,8,9]]
Output:
2 3 1
5 6 4
8 9 7
Explanation: Rotate the matrix by one
1 2 3       2 3 1
4 5 6  =>  5 6 4
7 8 9       8 9 7
```

```
    vector<vector<int>> rotateMatrix(int k, vector<vector<int>> mat) {
        
        int m = mat.size();

         // Get the number of columns
        int n = m > 0 ? mat[0].size() : 0;
        
        vector< vector<int>> arr( m  , vector<int>( n , 0 ) );
        k %= n;
        
        
        for( int i=0 ; i<n ; i++ ){
            int ind = i-k;
            if( ind < 0 ){
                int j = n + ind;
                for( int l=0 ;  l<m ; l++ ){
                    arr[l][j] = mat[l][i];    
                }
                
            }
            else{
                for( int l=0 ;  l<m ; l++ ){
                    arr[l][ind] = mat[l][i];    
                }
            }
            
        }
        
        return arr;
        
        
    }
```
