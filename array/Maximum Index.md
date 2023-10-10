# Maximum Index

```
    int maxIndexDiff(int A[], int N) 
    { 
        int ans = INT_MIN;
        int ind = 0  ;
      
        int maxArr[N];
        maxArr[N-1] = A[N-1];
        for( int i=N-2 ; i>= 0 ; i-- ){
            maxArr[i] = max( A[i] , maxArr[i+1]);
        }
        
        int j = 0;
        while( ind < N && j < N  ){
            if(  ind < N &&  A[j] <= maxArr[ind]  ){
                ans = max( ans , ind - j );                
                ind++;
            }
            else 
                j++;
                
           
        }
        
        return ans;
    }
```
