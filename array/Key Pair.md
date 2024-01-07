# key Pair 

```
	bool hasArrayTwoCandidates(int arr[], int n, int x) {
	    unordered_map<int, int> hash;
	    for( int i=0 ; i <n ; i++){
	        hash[arr[i]] += 1;
	    }
	    for( int i=0 ; i<n ; i++ ){
	        int rem = x - arr[i];
	        if( hash.find( rem ) != hash.end() ){
	            if( rem == arr[i] && hash[rem] < 2 )
	                continue;
	           return true;
	        }
	    }
	    
	    return false;
	}
```
