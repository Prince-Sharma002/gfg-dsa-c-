# IPL 2021 - Match Day 2
### Example
```
N = 9, K = 3
arr[] = 1 2 3 1 4 5 2 3 6
Output: 
3 3 4 5 5 5 6
```

### Code
```

    vector<int> max_of_subarrays(vector<int> arr, int n, int k) {
        
        int max = INT_MIN;
        vector<int> ans;
        deque<int> q;
        // for first window
        for( int i=0 ; i<k ; i++ ){
            if( arr[i] > max )
                max = arr[i];
            q.push_back( arr[i] );
        }
        ans.push_back( max );
        
        int first;
        int last;
        // remaining windows
        for( int i=k ; i<n ; i++ ){
            
            first = q.front();
            q.push_back( arr[i] );
            q.pop_front();
            
            if( arr[i] > max ){
                 ans.push_back( arr[i] );
                 max = arr[i];
            }
            
            else if( first == max ){
                max = -1;
                for( int j=i ; j >= i-k+1 ; j-- ){
                    if( arr[j] > max )
                        max = arr[j];
                }
                ans.push_back( max );
            }
            else
                ans.push_back( max );
                

        }
        return ans;
    }
```











