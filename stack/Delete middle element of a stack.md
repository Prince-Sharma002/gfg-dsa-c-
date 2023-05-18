# Delete middle element of a stack
### Example
```
Input: 
Stack = {1, 2, 3, 4, 5}
Output:
ModifiedStack = {1, 2, 4, 5} 

Input: 
Stack = {1 2 3 4}
Output:
ModifiedStack = {1 3 4}
```

### Code
```
    void deleteFun(stack<int>&s , int ind , int sizeOfStack ){
        if(ind == sizeOfStack / 2  ){
            s.pop();
            return ;
        }
        
        
        
        int a = s.top();
        s.pop();
        
        deleteFun(s , ind+1, sizeOfStack );
        
        s.push( a );
        
    }
    
    //Function to delete middle element of a stack.
    void deleteMid(stack<int>&s, int sizeOfStack)
    {

        deleteFun( s , 0 , sizeOfStack );
            
        
    }
```











