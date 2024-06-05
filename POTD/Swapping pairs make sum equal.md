```
Input: n = 6, m = 4, a[] = {4, 1, 2, 1, 1, 2}, b[] = (3, 6, 3, 3)
Output: 1
```

```
    int bs( int b[] , int m ,  int key ){
        int s = 0;
        int e = m-1;
        
        while( s < e ){
            int mid = ( s + e )/2;
            if( b[mid] == key )
                return 1;
            else if( b[mid] < key )
                s = mid+1;
            else 
                e = mid-1;
        }
        
        return -1;
        
    }
  
    int findSwapValues(int a[], int n, int b[], int m) {
        sort( a , a+n );
        sort( b , b+m );
        
        
        int suma = 0 ; int sumb = 0;
        for( int i=0 ; i<n ; i++ ){
            suma += a[i];            
        }
        
        for( int j=0 ; j<m ; j++ ){
            sumb += b[j];
        }
        
        int diff = suma - sumb;
        
        if( diff == 0 )
            return 1;
        
        
        if (diff % 2 != 0) return -1;
        
        if( diff < 0 )
            diff = diff * -1;
            
        for( int i=0 ; i<n ; i++ ){
            
            int temp = bs( b , m , diff - a[i] );
            if( temp == 1 )
                return 1;
        }
        
        return -1;
        
        
    }
```
