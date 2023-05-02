# Remove duplicate element from sorted Linked List

### Example
```
Input:
LinkedList: 2->2->4->5
Output: 2 4 5
```

### Code
``` 
//Function to remove duplicates from sorted linked list.
Node *removeDuplicates(Node *head)
{
    Node* temp = head;
    while( temp->next != NULL )
    {
        if( temp->data == temp->next->data ){
            Node* NodeToDelete = temp->next;
            temp->next = temp->next->next;
            delete NodeToDelete;
        }
        else
            temp = temp->next;
    }
    
    return head;
}
```











