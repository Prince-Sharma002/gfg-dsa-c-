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










