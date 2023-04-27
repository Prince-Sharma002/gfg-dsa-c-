# Linked List Operations
``` 
class Node{
    
    public:
    int data;
    Node* next;
    
    Node( int data ){
        this->data = data;
        this->next = NULL;      
    }  
};

// insertion of node
void insertionAtTail(Node* &tail , int data ){
    Node* node = new Node(data);
    tail->next = node;
    tail =  node;
}


void insertionAtHead( Node* &head , int data ){
    Node* node = new Node( data );
    node->next = head;
    head = node;
}

void insertAtMiddle( Node* head , int data , int idx ){
    Node* node = new Node( data );
    Node* temp = head;
    while( idx > 1 ){
        temp = temp->next;
        idx--;
    }
    node->next = temp->next;
    temp->next = node;
}

// deletion of node
void deletionAtHead( Node* &head ){
    Node* temp = head->next;
    delete head;
    head = temp;
}

void deletionAtTail( Node* head , Node* &tail ){
    Node* temp = head;
    while( temp->next->next  != NULL ){
        temp = temp->next;
    }
    Node* NodeToDelete = temp->next;
    delete NodeToDelete;
    temp->next = NULL;
    tail = temp;

}

void deletionAtMidddle( Node* head , int idx ) {
    Node* temp = head;
    while( idx > 1 ){
        temp = temp->next;
        idx--;
    }
    Node* NodeToDelete = temp->next;
    temp->next = temp->next->next;
    delete NodeToDelete;

}


void printing( Node* head ){
    Node* temp = head;
    while( 1 > 0 ){
        cout  << temp->data << "->";
        if(temp->next == NULL){
            cout << "NULL";
            return ;
        }
            
        temp = temp -> next;
    }
}

int main() {
    
    Node* node1 = new Node(1);
    
    Node* head = node1;
    Node* tail = node1; 
    
    insertionAtTail(tail , 2);
    insertionAtTail(tail , 3);
    insertionAtTail(tail , 4);
    insertionAtHead(head , 5);
    insertionAtHead(head , 6);
    insertAtMiddle( head , 9 , 3 );
    deletionAtHead( head );
    deletionAtTail(head , tail );
    deletionAtMidddle(head , 2);
    printing( head );
}
```











