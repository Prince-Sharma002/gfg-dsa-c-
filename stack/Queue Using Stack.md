# Queue using Stack

```
class Queue {
    stack<int> input, output;
public:

    void enqueue(int x) {
       input.push( x );
    }

    int dequeue() {
       
        return peek();
        
    }
    
    int peek( ){
        if( !output.size() ){
            while( input.size() ){
                output.push( input.top() ); 
                input.pop();
            }    
            int d = output.top();
            output.pop();
            return d;
        }
            int d = output.top();
            output.pop();
            return d;        
    }
};
```
