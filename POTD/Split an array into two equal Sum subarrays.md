```
    bool canSplit(vector<int>& arr) {
        int totalsum = 0;
        int n = arr.size();
        for( int i=0 ; i<n ; i++ ){
            totalsum += arr[i];
        }
        
        int s = 0;
        for( int i=0 ; i<n; i++ ){
            s += arr[i];
            if( s == totalsum - s )
                return true;
        }
        
        return false;
    }
```
