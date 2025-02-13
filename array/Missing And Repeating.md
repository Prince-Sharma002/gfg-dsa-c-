```
Input: arr[] = [2, 2]
Output: [2, 1]
Explanation: Repeating number is 2 and smallest positive missing number is 1.
```

```
vector<int> findTwoElement(vector<int>& arr) {
        int n = arr.size();
        vector<int> count( n , 0 );
        vector<int> ans;
        
        for( int i=0 ; i<n ; i++ ){
            count[ arr[i] - 1 ]++;
        }
        
            int mis;
            int rep;
        for( int i=0 ; i< n; i++ ){
            if( count[i] == 0 )
                mis = i+1;
            if( count[i] == 2 )
                rep = i+1;
        }
        
        ans.push_back( rep );
        ans.push_back( mis );
        
        return ans;
    }
```
