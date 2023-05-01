# Nth node from end of linked list

### Example
```
Input:
N = 2
LinkedList: 1->2->3->4->5->6->7->8->9
Output: 8
```

### Code
``` 
//Function to find the data of nth node from the end of a linked list.
int getNthFromLast(Node *head, int n)
{
    int count = 1;
    Node* temp = head;
    while( count < n ){
        temp = temp->next;
        count++;
        if( temp == NULL)
            return -1;
    }
    
    Node* ans = head;
    while( temp->next != NULL ){
        temp = temp->next;
        ans = ans->next;
    }
    
    return ans->data;
}

```











