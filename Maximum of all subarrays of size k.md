```
Input:
N = 9, K = 3
arr[] = 1 2 3 1 4 5 2 3 6
Output: 
3 3 4 5 5 5 6 

    vector <int> max_of_subarrays(int *arr, int n, int k)
    {

        vector<int> ans;
        deque<int> dq;

        for( int i=0 ; i<k ; i++ ){
            while( !dq.empty() && arr[dq.back()] < arr[i] )
                dq.pop_back();
            dq.push_back( i );
        }        
        
        for( int i=k ; i<=n ; i++ ){
            ans.push_back( arr[dq.front()] );
            
            while( !dq.empty() && dq.front() <= i-k )
                dq.pop_front();
            
            while( !dq.empty() && arr[dq.back()] < arr[i] )
                dq.pop_back();
            
            dq.push_back(i);
            
        }
  
        return ans;
    }
```
