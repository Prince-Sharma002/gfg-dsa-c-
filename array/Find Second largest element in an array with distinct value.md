# Find Second largest element in an array with distinct value

```
int print2largest(int arr[], int n) {
	    int max1 = -1 , max2= -1;
	    for(int i=0 ; i<n ; i++ ){
	        if(arr[i] <= max1 ){
	            
	            if( arr[i] == max1 )
	                continue;
	            else if( arr[i] < max2 )
	                continue;
	            else
	                max2 = arr[i];
	        }
	        else{
	            max2 = max1;
	            max1 = arr[i];
	        }
	    }
	    
	    return max2;
}
```


