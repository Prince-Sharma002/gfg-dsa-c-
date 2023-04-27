# Linked List Insertion
``` 
https://www.geeksforgeeks.org/insertion-in-linked-list/

//Function to insert a node at the beginning of the linked list.
Node *insertAtBegining(Node *head, int x) {
           
        Node* node = new Node( x );
        
        if( head == NULL )
            return node;
        
        node->next = head;
        head = node;
        return node;
}
    
    
//Function to insert a node at the end of the linked list.
Node *insertAtEnd(Node *head, int x)  {
        Node* node = new Node( x );
        Node* temp = head;
        if( head == NULL )
            return node;
            
        while(temp->next != NULL ){
            temp = temp->next;
        }
        
        temp->next = node;
        node->next = NULL;
        return head; 
}
```











