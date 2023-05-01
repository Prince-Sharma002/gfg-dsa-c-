# Check If Circular Linked List

### Example
```
Input:
LinkedList: 1->2->3->4->5
(the first and last node is connected,
i.e. 5 --> 1)
Output: 1
```

### Code
``` 
/* Should return true if linked list is circular, else false */
bool isCircular(Node *head)
{
   Node* temp = head->next;
   if(head == NULL)
        return false;
   while( temp != NULL ){
        if( temp == head )
            return true;
        
        if( temp == NULL )
            return false;
        temp = temp->next;
   }
}

```











