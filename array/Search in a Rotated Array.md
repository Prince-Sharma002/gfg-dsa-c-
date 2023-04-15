# Search in a Rotated Array

```
int main() {

    // Input  : arr[] = {5, 6, 7, 8, 9, 10, 1, 2, 3}
    // Output : Found at index 5
    
    int arr[] = { 5, 6, 7, 8, 9, 10, 1, 2, 3};
    int n = sizeof(arr)/sizeof(arr[0]);
    int key = 10;
    
    int mid;
    int l=0 ; int h = n-1;
    while( l <= h ){
        mid = (l+h)/2;
        if( arr[mid] < arr[mid-1] && arr[mid] < arr[mid+1] )
            break;
        if( l >= h )
            break;    
        else if( arr[mid] > arr[0]  )
            l = mid+1;
        else if( arr[mid] < arr[n-1]  )
            h = mid-1;
                    
    }
    
   
    if( arr[0] <= key && arr[mid-1] >= key ){
        l = 0; h = mid-1;
    }
    else{

        l = mid; h = n-1;      
    }
    

    int f = 0;
    while( l <= h ){
        
        mid = (l+h)/2;
        if( arr[mid] == key ){
            f = 1;
            break;
        }
        
            
        else if( arr[mid] > key )
            h = mid-1;
        else if( arr[mid] < key )
            l = mid+1;
        else
            break;
                    
    }
    
    if( f  )
        cout<< "pivot element is " << mid;
    else
        cout<< "pivot element is " <<  -1;

    
}
 
```











