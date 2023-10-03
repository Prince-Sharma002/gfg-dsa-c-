# Minimum element in a sorted and rotated array

```
    int findMin(int arr[], int n){
        int s = 0 ; 
        int e = n-1;
        

        if( arr[n-1] < arr[n-2] && arr[n-1] < arr[0] )
            return arr[n-1];
        
        while( s <= e  ){
            int mid = (s+e)/2;
            int ele = arr[mid];
            if( arr[mid-1]  > ele && arr[mid+1] > ele )
                return ele;
            
            if( ele < arr[e]  )
                e = mid-1;
            else s = mid+1;
        }
        
        return arr[0];
        
    }
```
