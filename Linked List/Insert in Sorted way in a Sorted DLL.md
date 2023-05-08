# Insert in Sorted way in a Sorted DLL

### Example
```
Input:
L1 = 10->20->40->50
x = 15
Output: L1 = 10->15->20->40->50
// function should insert a new node in sorted way in
// a sorted doubly linked list
// Return the head after insertion
// Node* sortedInsert(Node * head, int x)
```

### Code
``` 
// function should insert a new node in sorted way in
// a sorted doubly linked list
//Return the head after insertion
Node* sortedInsert(Node * head, int x)
{
	Node* temp = head;
	Node *node=getNode(x);
	
    // check for null ll
	if(head == NULL)
	    return node;
    // check both if single element ll or first element greater than x 	
    else if( head->next == NULL || head->data > x ){
        if( head->data > x  ){
            head->prev = node;
            node->next = head;
            return node;
        }
        else{
            head->next = node;
	        node->prev = head;
	        return head;
        }
    }
	
	while( 1 ){
	    if( temp->next == NULL ){
	        temp->next = node;
	        node->prev = temp;
	        break;
	    }
	    else if( temp->next->data > x ){
	        node->next = temp->next;
	        temp->next->prev = node;
	        temp->next = node;
	        node->prev = temp;
	        break;
	    }
	    else
	        temp = temp->next;
	}
	
	return head;
}; 
```











