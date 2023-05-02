# Find length of Loop

### Example
```
Input:
N = 10
value[]={25,14,19,33,10,21,39,90,58,45}
C = 4
Output: 7
```

### Code
``` 
//Function to find the length of a loop in the linked list.
int countNodesinLoop(struct Node *head)
{
    Node* slow = head;
    Node* fast = head->next;
    
    while( slow != fast ){
        if( !fast || !fast->next )
            return 0;
        slow = slow->next;
        fast = fast->next->next;
    }
    
    Node* loopend = slow;
    int count = 1;
    slow = slow->next;
    while( slow != loopend ){
        count++;
        slow = slow->next;
    }
    return count;
    
}
```











