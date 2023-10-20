# Number of subarrays whose minimum and maximum are same

```
    long long int numberOfways(int a[], int n)
    {
        
        long long int ans = 0;
        
        int similar =  0;
        for( int i=0 ; i<n ; i++ ){
            if( i == 0 ){
                similar = 1;
            }
            else{
                if( a[i] == a[i-1] )
                    similar++;
                else{
                    ans += similar*(similar+1)/2;
                    similar = 1;
                }
            }
            
            if( i == n-1 ){
                ans += similar*(similar+1)/2;
            }
            
            
        }
        
        return ans;
    }
```
