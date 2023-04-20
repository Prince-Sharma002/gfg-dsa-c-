# Sort an array of 0s, 1s and 2s

```
int main() {

    // input : arr[]= {0 2 1 2 0}
    // output : 0 0 1 2 2
    int arr[] = {0 ,2 ,1, 2 ,0};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    int i=0 ; int j=0 ; int k=n-1;
    
    while( i <= k ){
        
        
        if( arr[i] == 0  && arr[j] == 0 && i==j ){
            i++; j++;
            continue;
        }
        if( arr[i] == 1 && arr[j] == 1 && i==j ){
            i++;
            continue;
        }
        if( arr[i] == 1 ){
            i++;
            continue;
        }
            
        if( arr[i] == 0 && arr[j] == 1 ){
            swap( arr[i] , arr[j] );
            i++; j++;
            continue;
        }
        
        
        if( arr[i] == 2 ){
            swap( arr[i] , arr[k] );
            k--;
        }
      
    }

    // printing array
    for( int i=0 ; i<n ; i++ ){
        cout << arr[i] << " ";
    }
    
    
}
```











