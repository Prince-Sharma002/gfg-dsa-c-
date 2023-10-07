# Triplet Sum in Array

```
    bool find3Numbers(int A[], int n, int X)
    {
        sort( A , A+n);
        
        for( int i=0 ; i<n ; i++ ){
            int j = i+1 ; int k = n-1;
            while( j < k ){
                if( A[i] + A[j] + A[k] == X )   return 1;
                else if( A[i] + A[j] + A[k] < X ) j++;
                else k--;
                
            }
        }
        return 0;
    }
```
