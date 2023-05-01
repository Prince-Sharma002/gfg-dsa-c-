# Delete node in Doubly Linked List

### Example
```
LinkedList = 1 <--> 3 <--> 4 
x = 3
Output: 1 3  
```

### Code
``` 
    Node* deleteNode(Node *head, int x)
    {
      int count = 1;
      Node* temp = head;
      
      while( count != x ){
          count++;
          temp = temp->next;
      }
      if(x == 1){
          temp->next->prev = NULL;
          head = temp->next;
      }
      else if( temp->next == NULL ){
          temp->prev->next = NULL;
      }
      else{
        temp->prev->next = temp->next;
        temp->next->prev = temp->prev;
      }
      delete temp;
      return head;
    }

```











