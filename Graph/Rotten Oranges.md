# Rotten Oranges

```
    int orangesRotting(vector<vector<int>>& grid) {
        int n = grid.size();
        int m = grid[0].size();
        
        int row[] = {-1 , 0 , 1 , 0};
        int col[] = {0 , 1 , 0 , -1};
        
        int ans = 0;
        
        queue<pair<int,int>> q;
        for( int i=0 ; i<n ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                if( grid[i][j] == 2 )
                    q.push( {i , j });
            }
        }
        
        q.push( {-1 , -1});
        
        while( !q.empty() ){
            int i = q.front().first;
            int j = q.front().second;
            q.pop();
            
            
            
            if( i == -1 && j == -1 && q.size() != 0 ){
                ans += 1;
                q.push({-1 , -1});
                continue;
            }
                
            
            for( int k=0 ; k<4 ; k++ ){
                int nrow = i + row[k];
                int ncol = j + col[k];
                if( nrow >=0 && ncol >=0 && nrow <n && ncol <m && grid[nrow][ncol] == 1 ){
                    q.push( {nrow , ncol });
                    grid[nrow][ncol] = 2;
                }
            }
            
        }
        
        
        for( int i=0 ; i<n ; i++ ){
            for( int j=0 ; j<m ; j++ ){
                if( grid[i][j] == 1)
                    return -1;
            }
        }
        
        return ans;
        
        
    }
```
