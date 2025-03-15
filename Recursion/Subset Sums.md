```
Input: arr[] = [2, 3]
Output: [0, 2, 3, 5]
Explanation: When no elements are taken then Sum = 0. When only 2 is taken then Sum = 2. When only 3 is taken then Sum = 3. When elements 2 and 3 are taken then Sum = 2+3 = 5.
```

```
    void solve( int i , int sum , int n , vector<int> arr , vector<int>& ans  ){
        if( i == n )
        {   
            ans.push_back( sum );
            return ;
        }
        
        solve( i+1 , sum + arr[i] , n , arr , ans  );
        solve( i+1 , sum  , n , arr , ans  );
        
        
    }
    
    vector<int> subsetSums(vector<int>& arr) {
        vector<int> ans;
        int n= arr.size();
        solve( 0 , 0 , n , arr , ans  );
        
        return ans;
    }
```
