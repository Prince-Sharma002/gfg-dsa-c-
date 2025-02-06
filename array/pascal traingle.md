```
 vector<int> generateRow( int n ){
        vector<int> ans;
        ans.push_back( 1 );
        int a = 1;
        for( int i=1 ; i<n ; i++ ){
            a = a * (n-i);
            a = a/i;
            ans.push_back(a); 
        }

        return ans;
    }

    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ans;
        for( int i=1 ; i<= numRows ; i++ ){
            ans.push_back( generateRow(i) );
        }

        return ans;
    }
```
