# Sublist Search (Search a linked list in another list)
### Example
```
Input: list1 =  10->20
       list2  = 5->10->20
Output : LIST FOUND
```

### Code
``` 
bool subset( Node* head1, Node* head2 ){
    Node* ptr1 = head1;
    Node* ptr2 = head2;
    
    while( ptr2 != NULL){
        if( ptr1->data  == ptr2->data ){
            while( ptr1 != NULL || ptr2 != NULL ){
                ptr1 = ptr1->next;
                ptr2 = ptr2->next;
                if(ptr1 == NULL )
                    return true;
                if( ptr1->data == ptr2->data){
                    continue;
                }
                else{
                    ptr1 = head1;
                    break;
                }  
            }
            
            if(ptr1 == NULL )
                return true;
            if( ptr2 == NULL )
                return false;
        }
        else
            ptr2 = ptr2->next;
        
    }
    
    return false;
}

```











