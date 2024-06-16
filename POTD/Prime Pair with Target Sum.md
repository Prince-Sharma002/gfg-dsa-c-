```
Input: n = 10
Output: 3 7
```

```
    bool checkPrime( int n ){
        // Corner case
        if (n <= 1)
            return false;
     
        // Check from 2 to n-1
        for (int i = 2; i <= n / 2; i++)
            if (n % i == 0)
                return false;
     
        return true;
    }

    
    
    vector<int> getPrimes(int n) {
        vector<int> primeNo;
        vector<int> ans;
        
        
        for( int i=2 ; i<n ; i++ ){
            if( checkPrime(i) ){
                primeNo.push_back( i );
                int diff = n - i;
                if (checkPrime(diff) ){
                    ans.push_back( i  );
                    ans.push_back( diff  );
                    
                    return ans;
                }
            }
        }
        
        ans.push_back( -1 ); 
        ans.push_back( -1 );
        
        return ans;
        
    }
```
