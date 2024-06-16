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
    
    int FindMaxSum(int arr[], int n)
    {
        vector<int> dp( n+1 , -1 );
        return solve( arr , n-1  , dp );
    }
```
