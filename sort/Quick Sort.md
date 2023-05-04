# Quick Sort

### Example
```
Input: 
N = 5 
arr[] = { 4, 1, 3, 9, 7}
Output:
1 3 4 7 9
```

### Code
``` 
    public:
    //Function to sort an array using quick sort algorithm.
    void quickSort(int arr[], int low, int high)
    {
        if( low >= high  )
            return ;
        int pivot = partition( arr , low , high );
        quickSort( arr , low , pivot-1 );
        quickSort( arr , pivot+1  , high );
    }
    
    public:
    int partition (int arr[], int low, int high)
    {
        int pivotElement = arr[low];
        int count = 0;
        for( int i=low+1 ; i<=high ; i++ ){
            if( arr[i] <= pivotElement )
                count++;
        }
        
        int pivotIndex = low + count;
        swap( arr[low] , arr[pivotIndex] );
        
        int i = low; int j = high;
        while( i < pivotIndex && j > pivotIndex ){
            while( arr[i] <= pivotElement )
                i++;
            while( arr[j] > pivotElement )
                j--;
                
            if( i < pivotIndex && j > pivotIndex )
                swap( arr[i++] , arr[j--] );
        }
        
        return pivotIndex;
        
        
    }
```











