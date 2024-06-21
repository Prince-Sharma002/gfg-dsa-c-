```
Input: n = 6, str1 = ABCDGH and m = 6, str2 = AEDFHR
Output: 3
```

```
    // Function to find the length of longest common subsequence in two strings.
    int solve( int n, int m, string str1, string str2 , vector<vector<int>> &dp ){
        if( n == 0 || m == 0 )
            return 0;
            
        if(  str1[n-1] == str2[m-1]  ){
            return dp[n][m] = 1 + solve( n-1 , m-1 , str1 , str2 , dp);
        }
        
        if( dp[n][m] != -1 )
            return dp[n][m];
        
        
    
        return dp[n][m] = max( solve( n-1 , m , str1 , str2 , dp) , solve( n , m-1 , str1 , str2 , dp) );
        
    }
    
    int solveTab( int n, int m, string str1, string str2 ){
        
        int dp[n+1][m+1];
        
        for( int i=0 ; i<=n ; i++ ){
            for( int j=0 ; j<=m ; j++ ){
                
                if( i == 0 || j == 0 )
                    dp[i][j] = 0;
                else if( str1[i-1] == str2[j-1] )
                    dp[i][j] = 1 + dp[i-1][j-1];
                else
                    dp[i][j] = max( dp[i-1][j] , dp[i][j-1] ); 
                    
            }
            
        }
        
        return dp[n][m];
        
        
    }
    
    
    int lcs(int n, int m, string str1, string str2) {
        // vector<vector<int> > dp(n + 1, vector<int>(m + 1, -1));
        // return solve( n , m , str1 , str2 ,dp);
        
        return solveTab( n , m , str1 , str2);
    }
```
