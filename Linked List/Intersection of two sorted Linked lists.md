# Intersection of two sorted Linked lists

### Example
```
Input:
L1 = 10->20->40->50
L2 = 15->40
Output: 40
```

### Code
``` 
Node* findIntersection(Node* head1, Node* head2)
{
    Node* temp1 = head1;
    Node* temp2 = head2;
    Node *head=NULL, *tail=NULL;
    while( temp1 || temp2 ){
        if( temp1 == NULL || temp2 == NULL )
            break;
        

        if( temp1->data > temp2->data )
                temp2 = temp2->next;
        else if( temp2->data > temp1->data )
                temp1 = temp1->next;          
        else{
            if( head == NULL  ){
                head = tail = new Node(temp1->data);
            }    
            else{
                tail->next = new Node( temp1->data );
                tail = tail->next;
            }
            temp1 = temp1->next;  
            temp2 = temp2->next;
        }
      
    }
    
    return head;
    
}  
```











