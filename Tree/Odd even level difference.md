Odd even level difference

```
    int getLevelDiff(Node *root)
    {
        queue<Node*> q;
        q.push( root );
        
        int level = 0;
        int evenSum = 0 ; int oddSum = 0 ;
        int size = 0 ;
        while( !q.empty() ){
            level = !level;
            size = q.size();
            
            while( size > 0 ){
                Node* temp = q.front();
                q.pop();
                
                if( level )
                    oddSum += temp->data;
                else 
                    evenSum += temp->data;
                
                if( temp->left )
                    q.push( temp->left );
                if( temp->right )
                    q.push( temp->right );
                    
                size-- ;
                
            }
        }
        
        return oddSum - evenSum;
    }
```
