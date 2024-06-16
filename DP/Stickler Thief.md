```
Input:
n = 5
a[] = {6,5,5,7,4}
Output: 
15
```

```
    
    int solve( int arr[] , int n , vector<int> &dp ){
        if( n < 0 )
            return 0;
        
        if( n == 0 )
            return arr[0];
            
        if( dp[n] != -1  )
            return dp[n];
        
        int include = solve( arr , n-2 , dp ) + arr[n] ;
        int exclude = solve( arr , n-1 , dp )  + 0 ;
        
        dp[n] =  max( include , exclude );
        return dp[n];
    }
    
    
    int solve2( int arr[] , int n  ){
        vector<int> dp(n+1 , 0 );
        
        dp[0] = arr[0];
        
        for( int i=1 ; i<=n ; i++ ){
            int inc = dp[i-2] + arr[i];
            int exc = dp[i-1] + 0;
            
            dp[i] = max( inc , exc );
        }
        
        return dp[n];
        
    }
    
    int FindMaxSum(int arr[], int n)
    {
        vector<int> dp( n+1 , -1 );
        
        return solve2( arr , n-1 );
        
        return solve( arr , n-1  , dp );
    }
```
