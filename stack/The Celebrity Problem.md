# The Celebrity Problem
### Example
```
Input:
N = 3
M[][] = {{0 1 0},
         {0 0 0}, 
         {0 1 0}}
Output: 1
Explanation: 0th and 2nd person both
know 1. Therefore, 1 is the celebrity
```

### Code
```
bool check( vector<vector<int> >& M, int n , int i  ){
    // check for all zero
    for( int j=0 ; j<n ; j++ ){
        if(M[i][j] == 1)
            return false;
    }
    
    // check all know candidate
    for( int j=0 ; j<n ; j++ ){
        if( j == i )
            continue;
        
        if( M[j][i] == 0 )
            return false;
    }
    
    return true;
    
}

int celebrity( vector<vector<int> >& M, int n) 
{
    // check for first row
    if( check( M , n , 0 ) )
        return 0;
    
    // check for remaning row
    for( int i=0 ; i<n ; i++ ){
        if( M[0][i] == 1 && check( M , n , i ) )
            return i;
    }
    return -1;
}
```











