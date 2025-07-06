```
Input: n = 4
Output: [[2 4 1 3 ] [3 1 4 2 ]]
Explaination: There are 2 possible solutions for n = 4.
```


```
bool issafe(int row, int col, vector<vector<char>>& board) {
    int r = row, c = col;

    // Check left row
    c = col - 1;
    while (c >= 0) {
        if (board[row][c] == 'q') return false;
        c--;
    }

    // Check upper diagonal
    r = row - 1, c = col - 1;
    while (r >= 0 && c >= 0) {
        if (board[r][c] == 'q') return false;
        r--; c--;
    }

    // Check lower diagonal
    r = row + 1, c = col - 1;
    while (r < board.size() && c >= 0) {
        if (board[r][c] == 'q') return false;
        r++; c--;
    }

    return true;
}

    
    void solve( int col , vector<vector<char>>& board, vector<vector<int>>& ans, int n 
    , vector<int>& ds ){
        
        if( col == n ){
            ans.push_back( ds );
            return ;
        }
        
        
        for( int i=0 ; i<n ; i++ ){
            if( issafe( i, col, board ) ){
                board[i][col] = 'q';
                ds.push_back( i+1 );
                solve( col+1, board , ans , n , ds );
                board[i][col] = '.';
                ds.pop_back();
            }
        }
    }
  
    vector<vector<int>> nQueen(int n) {
        vector<vector<char>> board( n , vector<char>(n , '.') );
        vector<vector<int>> ans;
        vector<int> ds;
        solve( 0, board , ans , n , ds );
        
        return ans;
        
    }
```
