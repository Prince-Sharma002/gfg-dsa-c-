# Reverse a linked list
``` 
    //Function to reverse a linked list.
    struct Node* reverseList(struct Node *head)
    {
        if( head == NULL )
            return NULL;
            
        if( head->next == NULL )
            return head;
        
        struct Node* prev = NULL;
        struct Node* curr = head;
        struct Node* next = head->next;
        while( next != NULL ){
            curr->next = prev;
            prev = curr;
            curr = next;
            next = next->next;
        }
        
        curr->next = prev;
        return curr;
    }
```











