# Reorder an array according to given indexes


## using cyclic sort method
```
int main() {
    
    int arr[] = {50, 40, 70, 60, 90};
    int ind[] = {3,  0,  4,  1,  2};
    
    // Output: arr[]   = [40, 60, 90, 50, 70]
    //         ind[] = [0,  1,  2,  3,   4]
    
    int n = sizeof(arr)/sizeof(arr[0]);
    int i=0;
    int index;
    while( i < n ){
        if( ind[i] != i ){
            index = ind[i];
            swap( ind[i] , ind[index] );
            swap( arr[i] , arr[index] );
            continue;
        }
        i++;
    }
    
    // printing array
    for( int i=0 ; i<n ; i++ ){
        cout << arr[i] << " ";
    }
    
}
```



## BruteForce
```
int main() {
    
    // Input:  arr[]   = [50, 40, 70, 60, 90]
    // index[] = [3,  0,  4,  1,  2]
    // TC - 0(N) , SC -0(N)
    
    int arr[] = { 50, 40, 70, 60, 90 };
    int index[] = { 3,  0,  4,  1,  2 };
    int n = sizeof(arr)/sizeof(arr[0]);
    int temp[n] = {0};

    // storing value in temp array
    for( int i=0 ; i<n ; i++ ){
        temp[ index[i] ] = arr[i];
    }
    
    // copy value from temp to arr
    for( int i=0 ; i<n ; i++ ){
        arr[i] = temp[i] ;
    } 
    
    // printing array
    for( int i=0 ; i<n ; i++ ){
        cout << arr[i] << " ";
    }
    
}

```
