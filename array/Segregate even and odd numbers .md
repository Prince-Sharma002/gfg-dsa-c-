# Segregate even and odd numbers 


## Using Auxillary Space ( order maintain )
```
int main() {
    
    int arr[] = {1, 3, 2, 4, 7, 6, 9, 10 , 11};
    int n = sizeof(arr)/sizeof(arr[0]);
   
    int evnIndex = 0;
    int oddIndex = n-1;
    
    int temp[n];
    
    for(int i=0 , j=n-1 ; i<n , j>=0 ; i++ , j-- ){
        if( arr[i] % 2 == 0 ){
            temp[evnIndex] = arr[i];
            evnIndex++;
        }    
        if( arr[j] % 2 != 0 ){
            temp[oddIndex] = arr[j];
            oddIndex--;
        }
        
    }
    
    // printing array
    for( int i=0 ; i<n ; i++ ){
        cout<< temp[i] << endl;
    }
        
}

```

## Using Two pointer Approach ( order not maintain )
```

int main() {
    
    int arr[] = {1, 3, 2, 4, 7, 6, 9,10};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    int i = -1;
    int j = 1;
    for( int k=0 ; k<n ; k++ ){
        if(arr[j] % 2 == 0){
            i++;
            swap( arr[i] , arr[j] );
        }
        j++;
    }
    
    // printing array
    for( int i=0 ; i<n ; i++ ){
        cout<< arr[i] << endl;
    }
        
}
```





