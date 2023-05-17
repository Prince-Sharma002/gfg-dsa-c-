# Maximum product of indexes of next greater on left and right
### Example
```
Input : 5 4 3 4 5 
Output : 8 
For {5, 4, 3, 4, 5}, L[] = {0, 1, 2, 1, 0} and R[] 
= {0, 5, 4, 5, 0}, 
LRProduct = {0, 5, 8, 5, 0} and max in this is 8. 
```

### Code
```
void leftIndex( int arr[] , int n , int lArray[] ){
  
  stack<pair<int,int>> lstak;
  
  for( int i=0 ; i<n ; i++ ){
    
    while( !lstak.empty() and lstak.top().first <= arr[i] )
      lstak.pop();
      
    if( lstak.empty() )
      lArray[i] = 0;
    else
      lArray[i] =  lstak.top().second;
    
    lstak.push( { arr[i] , i+1 } );
  }
} 

void rightIndex( int arr[] , int n , int rArray[] ){
  
  stack<pair<int,int>> rstak;
  for( int i=n-1 ; i>=0 ; i-- ){
    
    while( !rstak.empty() and rstak.top().first <= arr[i] )
      rstak.pop();
      
    if( rstak.empty() )
      rArray[i] = 0;
    else
      rArray[i] =  rstak.top().second;
    
    rstak.push( { arr[i] , i+1 } );
  }
  
}

// Function to find maximum LR product
int LRProduct(int arr[], int n)
{
  int lArray[n] = {0};
	leftIndex( arr , n , lArray );
  
  int rArray[n] = {0};
  rightIndex( arr , n , rArray );
  
  
  int max = INT_MIN;
  for( int i=0 ; i<n ; i++ ){
    if( lArray[i]*rArray[i] > max )
      max = lArray[i]*rArray[i];
  }
  
  return max;
}



// Drivers code
int main()
{
	int arr[] = { 1 ,1 ,1, 1, 0 ,1 ,1, 1, 1, 1  };
	int n = sizeof(arr) / sizeof(arr[1]);

	cout << LRProduct(arr, n);

	return 0;
}
```











