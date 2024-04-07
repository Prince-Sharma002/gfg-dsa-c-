```
N = 7, K = 4
A[] = {1,2,1,3,4,2,3}
Output: 3 4 4 3
```

```
    vector <int> countDistinct (int A[], int n, int k)
    {
        unordered_map<int , int > um;
        vector<int> ans;
        
        for( int i=0 ; i<k ; i++ ){
            um[ A[i] ]++;
        }
        
        ans.push_back( um.size() );
        
    
        for( int i=1 ; i<n-k+1 ; i++ ){
            
            
            um[A[i-1]]--;
            if( um[A[i-1]] <= 0  ){
                um.erase( A[i-1] );
            }
            
            um[A[i+k-1]]++;
            ans.push_back( um.size() );
            
        }
        
        return ans;
        
    }
```
