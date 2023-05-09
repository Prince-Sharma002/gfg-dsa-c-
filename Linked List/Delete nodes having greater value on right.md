# Delete nodes having greater value on right

### Example
```
Input:
LinkedList = 12->15->10->11->5->6->2->3
Output: 15 11 6 3
```

### Code
``` 
Node *compute(Node *head)
    {
        if( head->next == NULL && head == NULL )
            return head;
        
        // reverse linked list
        Node *curr = head;
        Node *prev = NULL;
        Node *next;
        while(curr!=NULL)
        {
            next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
        }
        
        head = prev;
        
        
        // delete unwanted node
        curr = head;
        Node *maxNode = head;
        Node *temp;
    
         while (curr != NULL && curr->next != NULL)
         {
             if(curr->next->data < maxNode->data)
             {
                 temp = curr->next;
                 curr->next = temp->next;
                 free(temp);
             }
             else
             {
                 curr = curr->next;
                 maxNode= curr;
             }
         }
        
        // reversing again
         curr = head;
         prev = NULL;
         next;
         while(curr!=NULL)
         {
             next = curr->next;
             curr->next = prev;
             prev = curr;
             curr = next;
         }
    
         head = prev;
         
         // head of list can be returned now
    
        return head;
        
    }
```











