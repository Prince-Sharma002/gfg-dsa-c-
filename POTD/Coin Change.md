```
Input:
N = 3, sum = 4
coins = {1,2,3}
Output: 4
Explanation: Four Possible ways are: {1,1,1,1},{1,1,2},{2,2},{1,3}.
```

```
    long long int solve( int coins[], int N, int sum , vector<int> &dp ){
        if( sum == 0)
            return 1;
        
        if( sum < 0 )
            return 0;
        
        if( N <= 0 )
            return 0;
            
        if(dp[N-1] != -1 )
            return dp[N-1];
        
            
        dp[N-1] =  solve( coins , N-1 , sum ,dp ) + solve( coins , N , sum - coins[N-1] , dp);
        return dp[N-1];
        
    }
    
    long long int solve2(int coins[], int N, int sum, vector<vector<long long int>>& dp) {
        if (sum == 0)
            return 1;
    
        if (sum < 0)
            return 0;
    
        if (N <= 0)
            return 0;
    
        if (dp[N][sum] != -1)
            return dp[N][sum];
    
        dp[N][sum] = solve2(coins, N - 1, sum, dp) + solve2(coins, N, sum - coins[N - 1], dp);
        return dp[N][sum];
    }
    
    
  
    long long int count(int coins[], int N, int sum) {
        // return solve( coins , N , sum );
        
        // solve 2
        vector<vector<long long int>> dp(N + 1, vector<long long int>(sum + 1, -1));

        long long int result = solve2(coins, N, sum, dp);
        return result;
        
    }
```
