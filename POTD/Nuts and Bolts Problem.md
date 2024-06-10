```
The elements should follow the following order: { !,#,$,%,&,*,?,@,^ }

Input: n = 5, nuts[] = {@, %, $, #, ^}, bolts[] = {%, @, #, $ ^}
Output: 
# $ % @ ^
# $ % @ ^
```

```
    void matchPairs(int n, char nuts[], char bolts[]) {
        unordered_map<char , bool> mp;
        mp['!'] = false;
        mp['#'] = false;
        mp['$'] = false;
        mp['%'] = false;
        mp['&'] = false;
        mp['*'] = false;
        mp['?'] = false;
        mp['@'] = false;
        mp['^'] = false;
        
        for( int i=0 ; i<n ; i++ ){
            mp[ nuts[i] ] = true;
        }
        
        int j=0;
        vector<char> matchedVec;
        for( const auto i : mp){
            if( i.second  ){
                matchedVec.push_back( i.first );
            }
        }
        
        std::sort( matchedVec.begin() , matchedVec.end() );
        
        for( int i=0 ; i<matchedVec.size() ; i++ ){
            nuts[i] = matchedVec[i];
            bolts[i] = matchedVec[i];
        }
        
    }
```
