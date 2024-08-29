```
    int countNodesinLoop(Node *head) {
        Node* slow = head;
        Node* fast = head->next;
        
        while( slow != fast  ){
            if( !fast || !fast->next || !slow )
                return 0;
                
                
            slow = slow->next;
            fast = fast->next->next;
            
                
        }
        
        int c = 0;
        
        Node* temp = slow->next;
        while( temp != slow )
        {
            temp = temp->next;
            c++;
        }
        
        c++;
        return c;
    }
```
