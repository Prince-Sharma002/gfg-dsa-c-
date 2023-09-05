# Find whether path exist

```
    bool is_Possible(vector<vector<int>>& grid) 
    {
        queue< bfsStruct > q;
        
        int n = grid.size();
        
        for( int i=0 ; i<n ; i++ ){
            for( int j=0 ; j<n ; j++ )
                if( grid[i][j] == 1 ){
                    q.push( bfsStruct(i , j) );
                    break;
                }
        }
        
        while( !q.empty() ){
            bfsStruct node = q.front();
            q.pop();
            int x = node.i;
            int y = node.j;
            
            if( x < n && x >= 0 && y < n && y >= 0 ){
                
                if( grid[x][y] == 2 )
                    return true;
                
                if( grid[x][y] == 0 )
                    continue;
                    
                grid[x][y] = 0;
                q.push( bfsStruct(x-1 , y) );
                q.push( bfsStruct(x+1 , y) );
                q.push( bfsStruct(x , y-1) );
                q.push( bfsStruct(x , y+1) );
                
                
            }
            
            
        }
        
        return false;

    }
```
