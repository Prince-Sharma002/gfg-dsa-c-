```
Input:
N = 10
arr[] = {2,3,4,5,6,7,8,9,10,1}
Output: 1
Explanation: The array is rotated 
once anti-clockwise. So minimum 
element is at last index (n-1) 
which is 1.
```

```
    //Function to find the minimum element in sorted and rotated array.
    int minNumber(int arr[], int low, int high)
    {
        if( arr[0] < arr[high]) 
            return arr[0];
        
        int s = 0 ; int e = high;
        int n = high;
        while( true ){
            int mid = (s+e)/2;
            if( arr[mid] < arr[mid-1] && arr[mid] < arr[mid]+ 1)
                return arr[mid];
            else if( arr[mid] > arr[mid-1] && arr[mid] > arr[n] )
                s = mid+1;
            else if( arr[mid] > arr[mid-1] && arr[mid] < arr[n] )
                e = mid-1;
        }
        
    }
```
