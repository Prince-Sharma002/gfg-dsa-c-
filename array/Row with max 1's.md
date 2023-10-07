# Row with max 1's

```
	int rowWithMax1s(vector<vector<int> > arr, int n, int m) {
	    int cmax = 0;
	    int c = 0;
	    int ansIndex = 0;
	    for( int i=0 ; i<n ; i++ ){
	        c = 0;
	        for( int j=0 ; j<m ; j++ ){
	            if( arr[i][j] == 1 )
	                c++;
	           
	        }
	        
	        if( c > cmax ){
	            cmax = c;
	            ansIndex = i;
	        }
	        
	    }
	    
	   // check for if there is no 1's in array
	    if( ansIndex == 0 )
	    {
    	    for( int i=0 ; i<m ; i++ ){
    	        if( arr[0][i] == 1 )
    	            return ansIndex;
    	    }	    
    	    return -1;
	    }

	    
	    return ansIndex;
	}
```
