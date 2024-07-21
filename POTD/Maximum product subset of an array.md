```
vInput: arr[] = [-1, 0, -2, 4, 3]
Output: 24
Explanation: Maximum product will be ( -1 * -2 * 4 * 3 ) = 24
```

```
    long long int findMaxProduct(vector<int>& arr) {  
        int n = arr.size();
        int negNum = 0;
        int zeroNum = 0;
        long long int prod = 1;
        
        int maxi = INT_MIN;
        long long negprod = 1;
        for( int i=0 ; i<n ; i++ ){
            if( arr[i] < 0 ){
                negNum++;
                negprod *= arr[i];
                maxi = max( maxi , arr[i] );
            }
            else if( arr[i] == 0 )
                zeroNum++;
            else
                prod *= arr[i];
        }
        
        if( zeroNum == n )
            return 0;
        
        
        if( negNum == 1)
            return prod % 1000000007;
        
        //odd
        if( negNum % 2 != 0 )
        {
            negprod /= maxi;  
        }
        
        
        
        prod *= abs(negprod) % 1000000007;
        return prod;
        
    }
```
