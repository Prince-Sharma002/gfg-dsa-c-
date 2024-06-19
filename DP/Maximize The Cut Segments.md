```
Input:
N = 5
x = 5, y = 3, z = 2
Output: 2
```

```
    int solve( int n , vector<int> &dp , int x , int y , int z  , vector<int> var ){
        if( n == 0 )
            return 0;
        
        if( n < 0 )
            return INT_MIN;
        
        if( dp[n] != -1 )
            return dp[n];
            
        int maxi = INT_MIN; 
            
        for( int i=0 ; i<3 ; i++ ){
            int ans = solve( n - var[i] ,  dp , x , y , z , var  );
            
            if( ans != INT_MIN )
                maxi = max( maxi , ans+1 );
        }
        
        dp[n] = maxi;
        return dp[n];
        
    }
    
    int maximizeTheCuts(int n, int x, int y, int z)
    {
        vector<int> dp( n+1 , -1);
        vector<int> var;
        var.push_back( x );
        var.push_back( y );
        var.push_back( z );
        if( solve(  n , dp , x , y , z , var) == INT_MIN)
            return 0;
        return solve(  n , dp , x , y , z , var );
    }
```
