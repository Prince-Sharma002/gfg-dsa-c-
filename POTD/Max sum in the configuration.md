```
Input: n = 4, a[] = {8, 3, 1, 2}
Output: 29
```

```
    long long max_sum(int a[], int n) {
        long long arraySum = 0;
        for( int i=0 ; i<n ; i++ ){
            arraySum += a[i];
        }
        
        long long res = 0;
        for( int i=0 ; i<n ; i++ ){
            res += a[i]*i;
        }
        
        long long ans = res;
        
        for( int i=1 ; i<n ; i++ ){
            res = res -  (arraySum - a[i-1]) + 1LL *  a[i-1]*(n-1); 
            
            ans = max( res , ans );
        }
        
        return ans;
        
    }
```
