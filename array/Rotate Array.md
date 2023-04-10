# Rotate Array


## Using reversal Approach
```
void reverseFunc( int arr[] , int start , int end ){
    int mid  = (start + end) / 2;
    int s = start ; int e = end;
    for( int i=s ; i<=mid  ; i++ ){
        swap( arr[s] , arr[e] );
        s++; 
        e--;
    }
    
    }
    
    //Function to rotate an array by d elements in counter-clockwise direction. 
    void rotateArr(int arr[], int d, int n){
        
        if(d<n)
            d = d;
        else
            d = d%n;
        
        reverseFunc( arr , 0 , d-1);
        reverseFunc( arr , d , n-1 );
        reverseFunc(arr , 0 , n-1);
}

```







