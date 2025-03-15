```
Input: arr[] = [3, 34, 4, 12, 5, 2], target = 9
Output: true 
Explanation: Here there exists a subset with target sum = 9, 4+3+2 = 9.
```

```
    bool solve( int n , vector<int> arr , int  m  ){
        if( m == 0) return true;
        if( n < 0 ) return false;
        
        bool exclude = solve(n - 1, arr, m);

        // Include the current element only if it's ≤ remaining sum
        bool include = (m >= arr[n]) ? solve(n - 1, arr, m - arr[n]) : false;
        
        return exclude || include;
        
        
    }
    
    bool isSubsetSum(vector<int>& arr, int target) {
        int n = arr.size();
        return solve(  n-1 , arr , target );
    }
```
