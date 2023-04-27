# Search an element in a Linked List (Iterative and Recursive)
``` 
int search(Node* node , int x ){
    if( node->data == x) 
        return 1;
    if( node->next == NULL )
        return 0;
    
    return search( node->next , x);
}
```











