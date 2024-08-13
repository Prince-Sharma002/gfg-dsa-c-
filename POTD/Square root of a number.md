```
    long long int floorSqrt(long long int n) {
        
        if ( n == 0 || n == 1 )
            return n;
        
        long long int s=0;
        long long int e = n;
        long long int ans = 0;
        
        while( s <= e  ){
            long long int mid = (s+e)/2;
            if( mid*mid == n )
                return mid;
            else if( mid*mid  > n )
                e = mid-1;
            else {
                ans = mid;
                s = mid+1;
            }
        }
        
        return ans;
    }
```
