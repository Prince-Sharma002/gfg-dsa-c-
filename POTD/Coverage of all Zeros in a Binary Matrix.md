```
Input:
matrix = [[0, 1, 0],
          [0, 1, 1],
          [0, 0, 0]]
Output: 6
```

```
int findCoverage(vector<vector<int>>& matrix) {
    int n = matrix.size();
    int m = matrix[0].size();
    
    int ans = 0;
    
    for( int i=0 ; i<n ; i++ ){
        for( int j=0 ; j<m ; j++ ){
            
            if( matrix[i][j] == 1 )
                continue;
            if( i-1 >= 0 && matrix[i-1][j] )
                ans++;
            if( i+1 < n && matrix[i+1][j] )
                ans++;
            if( j-1 >= 0 && matrix[i][j-1] )
                ans++;
            if( j+1 < m && matrix[i][j+1] )
                ans++;
            
        }
    }
    
    
    return ans;
}
```
