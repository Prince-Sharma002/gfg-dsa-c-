# Stock Buy and Sell

```
    //Function to find the days of buying and selling stock for max profit.

struct solution{
    int buy;
    int sell;
};

vector<vector<int>> stockBuySell(vector<int> A, int n) {
    
  vector<vector<int>> ans;

    if(n == 1)
        return ans;

  solution store[n/2 + 1];
  
  int j=0; int count=0;
  while( j < n-1 ){
      
    while( j<n-1 && A[j] >= A[j+1] )
        j++;
    
    if( j == n-1 )
        break;
        
    store[count].buy = j;
    
    while( j<n-1 && A[j+1] <= A[j] )
        j++;
    
    j++;
    store[count].sell = j;
    count++;
    
  }
  
  if( count == 0 )
    return ans;
  
  for( int i=0 ; i<count ; i++ ){
      vector<int> temp;
      temp.push_back( store[i].buy );
      temp.push_back( store[i].sell );
      ans.push_back( temp );
  }
  
  return ans;
 
 
}
```
