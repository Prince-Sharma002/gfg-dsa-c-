# Move all zeroes to end of array

```
void pushZerosToEnd(int arr[], int n) {
	    int i=0 , j=0;
	    for( int k=0 ; k<n ; k++ ){
	        if( arr[i] != 0 && arr[j] != 0 ){
	            i++; j++;
	        }
	        else if( arr[i] == 0 && arr[j] != 0 ){
	            swap(arr[i] , arr[j] );
	            i++; j++;
	        }
	        else if(arr[i] == 0 && arr[j] == 0 )
	            j++;
	        else{
	            i++; j++;

	        }
	           
	    }
	}
```


