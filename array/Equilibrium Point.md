# Equilibrium Point

```
    int equilibriumPoint(long long a[], int n) {
        int s=0 ; int e = n-1;
        int lsum = 0; int rsum = 0;
        
        if( n == 1 )
            return 1;
        
        while( s < e ){
            if( !lsum && !rsum ){
            
                lsum = a[s]; rsum = a[e];
            }
            else{
                if( lsum < rsum ){
                    s++;
                    lsum += a[s];
                }
                else if( lsum == rsum ){
                    s++; e--;
                    if( s == e )
                        return s+1;
                    lsum = 0 ; rsum = 0;
                }
                else{
                    e--;
                    rsum += a[e];
                }
            }
            
        }
        return -1;
        
    }

```
