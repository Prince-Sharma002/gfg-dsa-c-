# Minimum swap to sort 

```
void heapify(vector<int>& nums, int n, int i) {
    int largest = i;

    int l = 2 * i + 1;
    int r = 2 * i + 2;

    if (l < n && nums[largest] < nums[l])
        largest = l;

    if (r < n && nums[largest] < nums[r])
        largest = r;

    if (largest != i) {
        swap(nums[largest], nums[i]);
        heapify(nums, n, largest);
    }
}

    
    void heapSort( vector<int>& nums , int n ){
        
        // build heap
        for( int i = n/2 -1 ; i>= 0 ; i-- ){
            heapify( nums , n , i );
        }
        
        for( int i=n-1 ; i>=0 ; i-- ){
            swap( nums[i] , nums[0] );
            
            heapify( nums , i , 0 );
        }
        
    }
    
    //Function to find the minimum number of swaps required to sort the array. 
	int minSwaps(vector<int>&nums)
	{
	    map<int, int> m;
	    int n = nums.size();
	    vector<int> arr = nums;
	    
	    
	   // storing index
	    for( int i=0 ; i<n ; i++ ){
	        m[nums[i]] = i;
	    }
	    
	    
	    heapSort( arr , n );
        
	    
	    int ans = 0 ;
	    for( int i=n-1 ; i>=0 ; i-- ){
            int sele = arr[i];
            int uele = nums[i];
            
            int index = m[sele];
            if( sele != uele ){
                ans++;
                swap( nums[index] , nums[i] );
                
                m[uele] = index;
                m[sele] = i;
            }
	    }
	    return ans;
	    
	    
	}
```
