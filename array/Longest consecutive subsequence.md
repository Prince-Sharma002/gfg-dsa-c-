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

```
    int longestConsecutive(vector<int>& arr) {
        unordered_set<int> st;
        int n = arr.size();
        
        if( n == 0 )
            return 0;
        
        int longest = 1;
        
        
        
        for( int i=0 ; i<n ; i++ ){
            st.insert( arr[i] );
        }
        
        
        for( auto it : st ){
            
            if( st.find( it -1 ) == st.end() ){
                int count = 1;
                int x = it;
                while( st.find( x+1 ) != st.end() ){
                    x++;
                    count++;
                }
                longest = max( longest, count );
            }
            
        }
        return longest;
        
    }
```
