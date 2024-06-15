```
Input: V = 30, M = 3, coins[] = {25, 10, 5}
Output: 2
Explanation: Use one 25 cent coin
and one 5 cent coin
```

```
	int solve( vector<int> coins , vector<int> &dp ,  int V  ){
	    if( V == 0 )
	        return 0;
	   
	    if( V < 0 )
	        return INT_MAX;
	  
	   if( dp[V] != -1 )
	        return dp[V];
	       
	   int mini = INT_MAX;
	    
	    for( int i=0 ; i<coins.size() ; i++ ){
	        
	        int ans = solve( coins , dp , V - coins[i] );
	        
	        if( ans != INT_MAX)
	           // increase number of coins by 1
	            mini = min( ans + 1, mini );
	       
	    }
	    
	    dp[V] = mini;
	    
	    return mini;
    
	    
	}
	
	
	int minCoins(vector<int> &coins, int M, int V) 
	{ 
	   
	   vector<int> dp( V + 1 , -1 );
	   if( solve(coins , dp , V )  == INT_MAX )
	        return -1;
	       
	       
	   return solve( coins , dp , V );
	   
	} 
```
