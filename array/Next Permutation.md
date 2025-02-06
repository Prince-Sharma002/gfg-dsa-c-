```
Input: arr = [2, 4, 1, 7, 5, 0]
Output: [2, 4, 5, 0, 1, 7]
Explanation: The next permutation of the given array is {2, 4, 5, 0, 1, 7}.
```

```
    void nextPermutation(vector<int>& arr) {
        int ind = -1;
        int n = arr.size();
        for( int i=n-2 ; i >= 0 ; i-- ){
            if( arr[i] < arr[i+1] )
            {
                ind = i;
                break;
            }
        }
        
        if( ind == -1 ){
            reverse( arr.begin() , arr.end() );
            return ;
        }
        
        for( int i=n-1 ; i>ind ; i-- ){
            if( arr[i] > arr[ind] ){
                swap( arr[i] , arr[ind] );
                break;
            }
        }
        
        reverse( arr.begin() + ind + 1 , arr.end() );
        return ;
        
    }
```
