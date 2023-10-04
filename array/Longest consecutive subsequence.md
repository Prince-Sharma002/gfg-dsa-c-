# Longest consecutive subsequence

```
   //Function to return length of longest subsequence of consecutive integers.
    int findLongestConseqSubseq(int arr[] , int N)
    {
        unordered_set<int> s;
        int c = 1;
        int ans  = 1;
        for( int i=0 ; i<N ; i++ ){
            s.insert( arr[i] );
        }
        
        for( int i=0 ; i<N ; i++ ){
            if( !(s.find( arr[i] - 1  ) != s.end()) ){
                c = 1;
                int j = 1;
                while( (s.find( arr[i] + j  ) != s.end()) ){
                    c = c+1;
                    j = j+1;
                }
                
                ans = max( c , ans );
                
            }
        }
        
        return ans;
    }
```
