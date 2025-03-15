```
Input: arr[] = [2, 4, 6, 8], target = 8
Output: [[2 2 2 2] [2 2 4] [2 6] [4 4] [8]]
Explanation: Total number of possible combinations are 5.
```

```
    
    void solve( int i , int sum , vector<int>& arr , int target,
    vector<vector<int>>& ans ,
        vector<int>& ds
    ){
        if( i == arr.size() ){
            if( sum == target )
                ans.push_back( ds );
            return ;
        }
        
        if( sum <= target ){
            ds.push_back( arr[i] );
            solve( i , sum + arr[i] , arr , target , ans , ds );
            ds.pop_back();
        }
        
        solve( i+1 , sum  , arr , target , ans , ds );
        
    }
    
    vector<vector<int>> combinationSum(vector<int> &arr, int target) {
        vector<vector<int>> ans;
        vector<int> ds;
        solve( 0 , 0 , arr , target , ans , ds );
        
        return ans;
    }
```
