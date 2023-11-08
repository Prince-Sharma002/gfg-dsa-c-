# Minimize the Heights II

```
    int getMinDiff(int arr[], int n, int k) {


        sort( arr , arr+n );
        
        int mini = arr[0];
        int maxi = arr[n-1];
        
        int ans = maxi - mini;
        
        for( int i=0 ; i<n ; i++ ){
            
            if( arr[i] - k < 0   )
                continue;
            
            mini = min( arr[i] - k , arr[0] + k );
            if (i > 0)
                maxi = max(arr[i-1] + k, arr[n-1] - k);
            else
                maxi = arr[n-1] - k; // If i is 0, take arr[n-1] - k as maxi

            
            ans = min( ans , maxi - mini );
            
        }
        
        return ans;
    }
```
