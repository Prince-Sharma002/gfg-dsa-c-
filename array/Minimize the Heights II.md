# Minimize the Heights II

```
    int getMinDiff(int arr[], int n, int k) {

        sort( arr , arr + n );
        
        int minEle = arr[0];
        int maxEle = arr[n-1];
        
        int ans = maxEle - minEle;
        
        for( int i=1 ; i<n ; i++ ){
            if( arr[i] - k < 0   )
                continue;
            
            minEle = min( arr[i] - k , arr[0] + k );
            maxEle = max( arr[i-1] + k , arr[n-1] - k );
            
            ans = min( ans , maxEle - minEle );
             
        }
        
        return ans;
        
    }
```
