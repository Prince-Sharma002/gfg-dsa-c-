# Radix Sort

```
int getMax( int arr[] , int n ){
    int maxi = arr[0];
    for( int i=1 ; i<n ; i++ ){
        if( arr[i] > maxi )
            maxi = arr[i];
    }
    
    return maxi;
}


void countsort( int arr[] , int n , int pos  ){
    
    int out[n];
    int count[10]= {0};
    int i;
    
    // store frequency
    for( i=0 ; i<n ; i++ ){
        count[ (arr[i]/pos) % 10 ]++ ;
    }
    
    // store cummulative frequency
    for( i=1 ; i<10 ; i++ ){
        count[i] += count[i-1];
    }
    
    // sort ans in out
    for( i=n-1 ; i>=0 ; i--  ){
        out[count[ (arr[i]/pos)%10 ] - 1] = arr[i]; 
        count[ (arr[i]/pos)%10 ]--; 
     }
     
    //  copy
    for (i = 0; i < n; i++) 
        arr[i] = out[i];
    
    
}


void radixSort(int arr[], int n) 
{ 
   
   int maxi = getMax( arr , n );
   for( int pos = 1 ; maxi/pos > 0 ; pos *= 10 ){
       countsort( arr , n , pos );
   }
   
   return ;
   
} 
```
