```
Input: n = 7, arr[] = {4, 3, 7, 8, 6, 2, 1}
Output: 3 7 4 8 2 6 1
Explanation: 3 < 7 > 4 < 8 > 2 < 6 > 1
```

```
    void zigZag(int n, vector<int> &arr) {
        bool flag = true;
        for( int i=0 ; i <= n-2 ; i++ ){
            if( flag )
            {
                if( arr[i] > arr[i+1])
                    swap( arr[i] , arr[i+1]);
            }
            else{
                if( arr[i] < arr[i+1])
                    swap( arr[i] , arr[i+1]);
            }
            
            flag  = !flag;
            
        }
        
    }
```
