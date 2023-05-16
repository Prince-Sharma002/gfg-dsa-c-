# Next Greater Element
### Example
```
Input: 
N = 4, arr[] = [1 3 2 4]
Output:
3 4 4 -1
Explanation:
In the array, the next larger element 
to 1 is 3 , 3 is 4 , 2 is 4 and for 4 ? 
since it doesn't exist, it is -1.
```

### Code
```
//Function to find the next greater element for each element of the array.
    vector<long long> nextLargerElement(vector<long long> arr, int n){
        stack<long long > st;
        vector<long long > ans (n);
        
        for( int i=n-1 ; i>=0 ; i-- ){
            
            while( !st.empty() && arr[i] >= st.top() ){
               st.pop(); 
            }
                
                
            if( st.empty() )
                ans[i] = -1;
                
            else
                ans[i] = st.top();
            
            st.push(arr[i]);
        }
        
        return ans;
        
        
        
    }
```











