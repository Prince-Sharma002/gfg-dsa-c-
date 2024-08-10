```
    // Function to rotate a linked list.
    Node* rotate(Node* head, int k) {
        if( k == 0)
            return head;
        
        Node* temp = head;
        int curr = 0;
        while( curr  < k-1 && temp != NULL ){
            curr++;
            temp = temp->next;
        }
        
        if( temp == NULL || temp->next == NULL )
            return head;
        
        Node* head2 = temp->next;
        temp->next = NULL;
        
        Node* temp2 = head2;
        while( temp2->next != NULL ){
            temp2 = temp2->next;
        }
        
        temp2->next = head;
        return head2;
    }
```
