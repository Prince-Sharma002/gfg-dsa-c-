# Stack using two queues
### Example
```
Input:
push(2)
pop()
pop()
push(3)
Output: 2 -1
```

### Code
```

//Function to push an element into stack using two queues.

queue<int> q1 , q2;

void QueueStack :: push(int x)
{
      q2.push( x );
      while( !q1.empty() ){
          q2.push( q1.front() );
          q1.pop();
      }
      
      queue<int> q = q1;
      q1 = q2;
      q2 = q;
}

//Function to pop an element from stack using two queues. 
int QueueStack :: pop()
{
    if( q1.empty() ) 
        return -1;
    
    int a = q1.front();
    q1.pop();
    return a;
} 

```











