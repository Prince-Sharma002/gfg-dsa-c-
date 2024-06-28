```
Input: 
arr[][] =  [[1, 0, 0], 
           [0, 1, 0],
           [1, 1, 0]]
Output: 1 R
```

```
    bool checkRow( int i  , int n , vector<vector<int>> &arr){
        for( int j=0 ; j<n/2 ; j++  ){
            if( arr[i][j] == arr[i][n-j-1] )
                continue;
            else 
                return false;
        }
        
        return true;
        
    }
    
    bool checkCol( int i , int n , vector<vector<int>> &arr ){
        for( int j=0 ; j<n/2 ; j++  ){
            if( arr[j][i] == arr[n-j-1][i] )
                continue;
            else 
                return false;
        }
        
        return true;
    }
    
    string pattern(vector<vector<int>> &arr) {
            
            int n = arr.size();
            // row
            for( int i=0 ; i<n ; i++  ){
                if( checkRow(i , n , arr) )
                    return to_string(i) + " R";
            }
            
            
            // column
            for( int i=0 ; i<n ; i++ ){
                if( checkCol( i , n , arr) )  
                    return to_string(i) + " C";
            }
            
            return "-1";
            
    }
```
