```
For example, consider the following ranges.
l[] = {2, 1, 3}, r[] = {5, 3, 9)
Ranges represented by the above arrays are.
[2, 5] = {2, 3, 4, 5}
[1, 3] = {1, 2, 3}
[3, 9] = {3, 4, 5, 6, 7, 8, 9}
```

```
    int maxOccured(int n, int l[], int r[], int maxx) {
        int arr[1000000];
        memset(arr, 0, sizeof(arr));
        for( int i=0 ; i<n ; i++ ){
            arr[ l[i] ] += 1;
            arr[ r[i] + 1 ] -= 1;
        }
        

        int ans = arr[ 0 ];
        int ind = 0; 
         
        for( int i = 1 ; i<=maxx ; i++ ){
            arr[i] += arr[i-1];
            
            if( ans < arr[i] ){
                ind = i;
                ans = arr[i];
            }
            
        }
        
        return ind;
    }
```
