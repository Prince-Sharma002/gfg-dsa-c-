# linked list implementation of stack
### Example
```
Stack s;
cout << "stack is empty " <<  s.isEmpty(); 
// return 1 means stack is empty
    
s.push(1);
s.push(2);
s.push(3);   // top element is 3

s.pop();     // delete top element that is 3

cout <<  endl;
cout << "top element is " << s.peek();  
// print top element 2
```

### Code
``` 
// C++ program for linked list implementation of stack
#include <bits/stdc++.h>
using namespace std;

class Node{
  public:
  int data;
  Node* next;
  Node( int data ){
      this->data = data;
      this->next = next;
  }  
};

class Stack{
    
  Node* top;
  public:
  Stack(){ top=NULL; }
  
  void push( int data ){
      
      Node* newNode = new Node( data );
      
      if( !newNode )
        return ;
      
      newNode->next = top;
      top = newNode;
      
  }
  
  bool isEmpty(){
      
      return top == NULL;
      
  }
  
  int peek(){
      
      if( top == NULL )
        return -1;
      
      return top->data;
      
  }
  
  void pop(){
      
      if(top == NULL)
        return ;
       
      Node* deleteTop = top;
      top = top->next;
      delete deleteTop; 
      
  }
    
};

int main()
{
    Stack s;
    cout << "stack is empty " <<  s.isEmpty(); // return 1 means stack is empty
    
    s.push(1);
    s.push(2);
    s.push(3);   // top element is 3
    
    s.pop();     // delete top element that is 3
    
    cout <<  endl;
    cout << "top element is " << s.peek();  // print top element 2
    
}
```











