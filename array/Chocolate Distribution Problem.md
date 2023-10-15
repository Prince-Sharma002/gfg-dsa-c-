# Chocolate Distribution Problem

```
    long long findMinDiff(vector<long long> a, long long n, long long m){
        
        sort(a.begin() , a.end() );
        long long ans = INT_MAX;
        long long s=0 ; long long e=m-1;
        while(e < n ){
            long long  diff = a[e] - a[s];
            ans = min( ans , diff );
            s++; e++;
        }
        
        return ans;
    } 
```
