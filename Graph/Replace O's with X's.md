# Replace O's with X's

```
bool isValid( int i , int j , int n , int m   ){
    if( i>= 0 && i<n && j>=0 && j<m)
        return true;
    return false;
}

    void dfs( int i , int j , int n , int m , vector<vector<char>>& mat ){
        if( isValid( i , j , n , m ) && mat[i][j] == 'O' ){
            mat[i][j] = '-';
            dfs( i+1 , j , n , m , mat );
            dfs( i-1 , j , n , m , mat );
            dfs( i , j-1 , n , m , mat );
            dfs( i , j+1 , n , m , mat );
        }
    }


    vector<vector<char>> fill(int n, int m, vector<vector<char>> mat)
    {
     
        for( int i=0 ; i<n ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                if( (i == 0 &&  mat[i][j] == 'O') || ( i == n-1 && mat[i][j] == 'O')
                    || ( j == 0 && mat[i][j] == 'O' ) || ( j == m-1 && mat[i][j] == 'O')    )
                    dfs( i , j , n , m , mat );
                    
            }
        }
        
        // changing all interior o
        for( int i=0 ; i<n ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                if( mat[i][j] == 'O' )
                    mat[i][j] = 'X';
                else if( mat[i][j] == '-')
                    mat[i][j] = 'O';
            }
        }
        
        return mat;
    }
```
