# Sort an array of 0s, 1s and 2s

```
    void sort012(int arr[], int n)
    {
        int i=0 ;int k = 0;
        int j = n-1;
        while( i <= j ){
if( arr[i] == 0  ){
                swap( arr[i] , arr[k] );
                i++; k++; 
            }
            else if( arr[i] == 2 ){
                swap( arr[i] , arr[j] );
                j--;
            }
            else if( arr[i] == 1 )
                i++ ;
            
        }
    }
```











