# Majority Element ( element that appears more than N/2 times in the array)

``` 
// input: A[] = {3,1,3,3,2} 
// Output: 3
// TC - 0(N)
int majorityElement(int a[], int size)
{
    
    int votes = 0 ;
    int candidate ; 
    for( int i=0 ; i<size ; i++ ){
        if( votes == 0 ){
            votes = 1;
            candidate = a[i];
        }
        else if( a[i] != candidate )
            votes--;
        else
            votes++;
    }
    
    int count = 0;
    for( int i=0 ; i<size ; i++ ){
        if( a[i] == candidate )
           count++; 
    }
    
    if( count > (size/2) )
        return candidate;
    else
        return -1;
    
}
```











