```
Input:
mat = [[6, 7, 8],
       [4, 6, 7],
       [1, 4, 6]]
Output: true
Explanation: The test case represents a 3x3 matrix
 6 7 8 
 4 6 7 
 1 4 6
```

```
bool isToeplitz(vector<vector<int>>& mat) {
    int n = mat.size();
    int m = mat[0].size();
    
    // Check each element with its bottom-right neighbor
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < m - 1; j++) {
            if (mat[i][j] != mat[i + 1][j + 1]) {
                return false;
            }
        }
    }
    
    return true;
}
```
