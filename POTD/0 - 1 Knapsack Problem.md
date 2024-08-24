```
Input: W = 4, val[] = {1,2,3}, wt[] = {4,5,1}
Output: 3
Explanation: Choose the last item that weighs 1 unit and holds a value of 3.
```

```
    
    int solve( int W, vector<int>& wt, vector<int>& val , int n ){
        if( W == 0 || n == 0 )
            return 0;
        
        if( wt[n-1] > W )
            return solve( W , wt , val , n-1);
        
        else
        {
            return max( solve( W , wt , val , n-1) ,
            val[n-1] + solve( W-wt[n-1] , wt , val , n-1) ); 
        }    
        
    }
    
    
    int knapSack(int W, vector<int>& wt, vector<int>& val) {
        int n= val.size();
        return solve( W , wt , val , n);
    }
```
