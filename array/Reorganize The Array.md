# Reorganize The Array


```
int * Rearrange(int *arr,int n){
        
    int i=0;
    while( i < n ){
        if(arr[i] == -1 ){
            i++;
            continue;
        }

        if(arr[i] != -1){
            if(arr[i] == i){
                i++;
                continue;
            }
            swap( arr[i] , arr[ arr[i] ]);
            if( arr[i] == -1)
                i++;
            if(arr[i] == i){
                i++;
                continue;
            }
        }
            
    }
    return arr;
}

```







