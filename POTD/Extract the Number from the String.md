```
Input: sentence="This is alpha 5057 and 97"
Output: 5057
Explanation: 5057 is the only number that does not have a 9.
```

```
    long long ExtractNumber(string sentence) {
        vector<long long> numberStore;
        bool flag = false;
        for( int i=0 ; i<sentence.length() ; i++ ){
            if( isdigit(sentence[i]) ){
                long long num = 0;
                while(  i<sentence.length() &&  isdigit(sentence[i])  ){
                    num = num*10 + int( sentence[i] - '0' );
                    if( int( sentence[i] - '0' ) == 9 ){
                        num = -1;
                        flag = true;
                    }
                    i++;
                }
                if( flag )
                    numberStore.push_back( -1 );
                else
                    numberStore.push_back( num );
                
            } 
            
            flag = false;
        }
        long long maxi = -1;
        for( int i=0 ; i<numberStore.size() ; i++ ){
            if( numberStore[i] > maxi )
                maxi = numberStore[i];
            
        }
        
        return maxi;
        
    }
```
