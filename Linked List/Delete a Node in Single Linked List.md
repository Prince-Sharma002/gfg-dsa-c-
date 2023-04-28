# Delete a Node in Single Linked List
``` 
// Input: 1 -> 3 -> 4   x = 3
// Output: 1 -> 3

Node* deleteNode(Node *head,int x)
{
    if( x == 1 ){
        Node* deleteNode = head;
        head = head->next;
        delete deleteNode;
        return head;
    }
    
    Node* temp = head;
    
    int count = 1;
    while( count != x-1 ){
        temp = temp->next;
        count++;
    }
    Node* deleteNode = temp->next;
    temp->next = temp->next->next;
    delete deleteNode;
    return head;
}

```











