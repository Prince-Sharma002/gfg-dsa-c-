# Finding middle element in a linked list

### Example
```
Input:
LinkedList: 1->2->3->4->5
Output: 3 
```

### Code
``` 
/* Should return data of middle node. If linked list is empty, then  -1*/
    int getMiddle(Node *head)
    {
        if(head == NULL)
            return -1;
            
        
        Node* fastPointer = head;
        Node* slowPointer = head;
        while( fastPointer != NULL && fastPointer->next != NULL ){
            fastPointer = fastPointer->next->next;
            slowPointer = slowPointer->next;
        }
        
        return slowPointer->data;

    }

```











