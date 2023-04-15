# Finding First Negative Element

```
// input arr - [ 1 2 3 5 9 6 8 13 -7 -11 ] 
// output - 8

// finding first negative number index using modify binary search 
    int s=0 ; int e=n-1;
    int mid = -1;
    int f = 0;
    while( s <= e ){
        mid = (s+e)/2;
        if(arr[mid] < 0 && arr[mid-1] >= 0 ){
            f = 1;
            break;
        }
            
        else if( arr[mid] < 0 && arr[mid-1] < 0  )
            e = mid-1;
        else if( arr[mid] >= 0 )
            s = mid+1;
    }
    
    if( f )
        cout << mid << endl;
    else
        cout << -1 << endl;
 
```











