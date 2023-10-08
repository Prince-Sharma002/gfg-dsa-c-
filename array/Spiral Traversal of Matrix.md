# Spiral Traversal of Matrix

```
    //Function to return a list of integers denoting spiral traversal of matrix.
    vector<int> spirallyTraverse(vector<vector<int> > matrix, int r, int c) 
    {
        vector<int> ans;
        
        int rowStart = 0 ; int colStart = 0;
        int rowEnd = r; int colEnd = c;
        
        while( rowStart < rowEnd && colStart < colEnd ){
            
            for( int i=colStart ; i<colEnd ; i++ )
                ans.push_back( matrix[rowStart][i] );
             rowStart++;
             
             for( int i=rowStart ; i<rowEnd ; i++ )
                ans.push_back( matrix[i][colEnd-1] );
             colEnd--;
             
             if( rowStart < rowEnd ){
                 for( int i=colEnd-1 ; i >= colStart ; i-- )
                    ans.push_back( matrix[rowEnd-1][i] );
                rowEnd--;                 
             }

            if( colStart < colEnd ){
                for( int i=rowEnd-1 ; i>=rowStart ; i-- )
                    ans.push_back( matrix[i][colStart] );
                colStart++;                
            }

         
        }
        
        return ans;
        
    }
```
