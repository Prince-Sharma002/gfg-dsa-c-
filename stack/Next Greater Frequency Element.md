# Next Greater Frequency Element
### Example
```
Input : a[] = [1, 1, 2, 3, 4, 2, 1] 
Output : [-1, -1, 1, 2, 2, 1, -1]
```

### Code
```
void NGF(int arr[], int res[], int n) {
  
  stack<int> st;
  map<int, int> freqmap;
  
  // store Frequency of Elements 
	for( int i=0 ; i<n ; i++ ){
    freqmap[arr[i]] += 1;
  }
  
  for( int i=n-1 ; i >= 0 ; i-- ){
    while( !st.empty() && freqmap[st.top() ] <= freqmap[ arr[i] ] )
      st.pop();
    
    if(st.empty())
      res[i] = -1;
    else
      res[i] = st.top();
    
    st.push( arr[i] );
    
  }

}
	
int main()
{
	int arr[] = {1, 1, 1, 2, 2, 2, 2, 11, 3, 3};
	int n = sizeof(arr) / sizeof(arr[0]);
	
	int res[n];
	NGF(arr, res, n);
	cout << "[";
	for(int i = 0; i < n; i++)
	{
		cout << res[i] << ", ";
	}
	cout << "]";

	return 0;
}
```











