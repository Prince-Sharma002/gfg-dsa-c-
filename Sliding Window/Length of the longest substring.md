```
Input:
S = "geeksforgeeks"
Output:
7
Explanation:
Longest substring is
"eksforg".
```

```
    int longestUniqueSubsttr(string S){
        
        int maxlen = 1 , currlen = 1;
        int visited[26];
        int prevInd;
        
        for( int i=0 ; i<26 ; i++ ){
            visited[i] = -1;
        }
        
        visited[ S[0] - 'a' ] = 0;
        
        for( int i=1 ; i<S.length() ; i++ ){
            
            // it contain index of previous element if exist 
            prevInd = visited[ S[i] - 'a' ];
            
            if( prevInd == -1 || i - currlen > prevInd ) 
                currlen++;
            
            else{
                if( currlen > maxlen )
                    maxlen = currlen;
                
                // moving currlen to next of prevInd + 1 
                currlen = i - prevInd;
            }
            
            visited[ S[i] - 'a' ] = i;
            
        }
        
        if( currlen > maxlen )
            maxlen = currlen;
            
        return maxlen;
        
        
    }
```
