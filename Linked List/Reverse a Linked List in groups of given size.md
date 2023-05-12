# Reverse a Linked List in groups of given size
### Example
```
Input:
LinkedList: 1->2->3->4->5
K = 3
Output: 3 2 1 5 4 
Explanation: 
The first 3 elements are 1,2,3 are reversed 
first and then elements 4,5 are reversed.Hence, 
the resultant linked list is 3->2->1->5->4.
```

### Code
``` 

// function of reversing k elements in LinkedList
struct node *reverse (struct node *head, int k)
{ 
    head = reversee(head , k);
    return head;
}


struct node* reversee( struct node* &head , int k ){
if( !head || !head->next )
    return head;
    
struct node* prev = NULL;
struct node* curr = head;
struct node* forw = head->next;
int a = 0;
while( a < k ){  
    curr->next = prev;
    prev = curr;
    curr = forw;
    a++;
    if(forw == NULL)
        break;
    forw = forw->next; 
}    
head->next = reversee( curr , k );
return prev;
}
```











