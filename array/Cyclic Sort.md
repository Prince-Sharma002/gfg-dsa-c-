# Cyclic Sort


## Applicable for array 1 to n elements( all elements should present )
```
int main() {
    
    // array should have all elements in range
    int arr[] = {3,4,6,5,1,2};
    int n = sizeof(arr)/sizeof(arr[0]);
    int i=0;
    int index;
    while( i < n-1 ){
        if( arr[i] != i+1 ){
            index = arr[i] - 1;
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










