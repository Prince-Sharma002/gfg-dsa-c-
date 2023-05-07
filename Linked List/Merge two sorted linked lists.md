# Merge two sorted linked lists

### Example
```
Input:
N = 4, M = 3 
valueN[] = {5,10,15,40}
valueM[] = {2,3,20}
Output: 2 3 5 10 15 20 40
```

### Code
``` 
//Function to merge two sorted linked list.
Node* sortedMerge(Node* head1, Node* head2)  
{  
    Node* head = new Node(0);
    Node* temp = head;
    Node* p1 = head1;
    Node* p2 = head2;
    while( p1 != NULL || p2 != NULL ){
        if( p1 == NULL ){
            temp->next = p2;
            break;
        }
        if( p2 == NULL ){
            temp->next = p1;
            break;
        }
        
        if(p1->data >= p2->data ){
            temp->next = p2;
            p2 = p2->next;
        }
        else{
            temp->next = p1;
            p1 = p1->next;
        }
        temp = temp->next;
    }

    
    return head->next;
    
}  
```











