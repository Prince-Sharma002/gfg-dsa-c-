# Detect Loop in linked list

### Example
```
N = 3
value[] = {1,3,4}
x(position at which tail is connected) = 2
Output: True 
```

### Code
``` 
//Function to check if the linked list has a loop.
bool detectLoop(Node* head)
{
    if( !head || !head->next )
        return false;
    
    Node* slow = head;
    Node* fast = head->next;
    
    while( slow != fast ){
        if( !fast || !fast->next )
            return false;
        slow = slow->next;
        fast = fast->next->next;
    }
    return true;
}
```











