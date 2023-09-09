# Unit Area of largest region of 1's

```
    //Function to find unit area of the largest region of 1s.
    bool isValid( int i , int j , int n , int m ){
        if( i>=0 && j>=0 && i<n && j<m )
            return true;
        return false;
    }
    
    int findMaxArea(vector<vector<int>>& grid) {
        int row[] = { 0,0,1,-1,1,1,-1,-1}; 
        int col[] = { 1,-1,0,0,1,-1,1,-1};
        
        queue<pair<int,int>> q;
        int n = grid.size();
        int m = grid[0].size();
        
        int ans = 0;
        
        for( int i=0 ; i<n ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                if( grid[i][j] == 1 ){
                    
                    grid[i][j] = 0;
                    q.push({i, j});
                    int count = 1;
                    
                    while( !q.empty() ){
                        
                        int r = q.front().first;
                        int c = q.front().second;
                        
                        q.pop();
                        
                        for( int k=0 ; k<8 ; k++ ){
                            int newr = r + row[k];
                            int newc = c + col[k];
                            
                            if( isValid( newr , newc , n , m ) && grid[newr][newc] == 1 ){
                                grid[newr][newc] = 0;
                                count += 1;
                                q.push( {newr , newc });
                                
                            }
                            
                        }
                        
                        
                    }
                    
                    ans = max( ans , count );
                    
                }
            }
        }
        
        return ans;
        
    }
```
