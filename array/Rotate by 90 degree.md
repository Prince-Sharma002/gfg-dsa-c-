```
Input: mat[][] = [[1, 2, 3],
                [4, 5, 6]
                [7, 8, 9]]
Output: Rotated Matrix:
[3, 6, 9]
[2, 5, 8]
[1, 4, 7]
```

```
    // Function to rotate matrix anticlockwise by 90 degrees.
    void rotateby90(vector<vector<int>>& mat) {
        int n = mat.size();
        int m = mat[0].size();
        
        int j = 1;
        // transpose matrix
        for( int i=0 ; i<n ; i++ ){
            int k = j;
            while( k < m ){
                swap( mat[i][k] , mat[k][i] );
                k++;
            }
            j++;
        }
        
        // reverse matrix
        int i=0 ; j=n-1;
        while( i < j  ){
            for( int k=0 ; k<m ; k++ ){
                swap( mat[i][k] , mat[j][k] );
            }
            
            i++; j--;
            
        }
        
    }
```
