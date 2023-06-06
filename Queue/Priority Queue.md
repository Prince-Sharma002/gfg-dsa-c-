# Priority Queue

### Example
```
enque( 10 , 2 );
enque( 14 , 4 );
enque( 16 , 4 );
enque( 12 , 3 );

Output : 
16
14
```

### using array
``` 
#include <bits/stdc++.h>
using namespace std;

class ele{
	public:
	int data;
	int priority;
};

ele pq[100000];
int len = -1;

void enque( int data , int priority ){
	len++;
	pq[len].data = data;
	pq[len].priority = priority;
}

int peek(){
	int ind = -1;
	int max_priority = INT_MIN;
	for( int i=0 ; i<len ; i++ ){
		
		if( ind > -1 && 
			max_priority == pq[i].priority && 
		 	pq[ind].data < pq[i].data ){
				 
			ind = i;
			
		}
		else if( pq[i].priority > max_priority ){
			max_priority = pq[i].priority;
			ind = i;
		}
	}
	
	return ind;
}

void dequee(  ){
	int ind = peek();
	for( int i = ind + 1 ; i< len ; i++ ){
		pq[i - 1] = pq[i]; 
	}
	len--;
}




int main(){
	enque( 10 , 2 );
	enque( 14 , 4 );
	enque( 16 , 4 );
	enque( 12 , 3 );
	
	cout <<  pq[peek()].data << endl;
	
	dequee();
	
	cout << pq[peek()].data << endl;
	
}
```

### using linked list
```
#include <bits/stdc++.h>
using namespace std;

class Node{
    
    public:
    int data;
    Node* next;
    int priority;
    
    Node( int data , int priority ){
        this->data = data;
        this->next = NULL;     
        this->priority = priority; 
    }  
};

Node* node = NULL;
Node* head = node;




Node* push( Node* &head , int x ,  int pri )
{
    Node* newNode = new Node(x , pri );
    if(head == NULL){
        head = newNode  ;
        return head;
    }
    Node* prev = NULL;
    Node* curr = head;
    while( curr != NULL ){
        if( curr->priority <= pri ){
			// handling same priority element
            if( curr->priority == pri && curr->data > newNode->data ){
                prev = curr;
                curr = curr->next;
                prev->next = newNode;
                newNode->next = curr;
                return head;
            }
			// handling first element
            if(prev == NULL){
                newNode->next = curr;
                head = newNode;
                return head;
            }
			// handling non same priority element
            prev->next = newNode;
            newNode->next = curr;
            return head;
        }
        else{
            if( curr->next  == NULL){
                curr->next = newNode;
                return head;
            }
            prev = curr;
            curr = curr->next;
        }

    }
    return head;

}


void printing( Node* head ){
    if( head == NULL )
        return ;
    Node* temp = head;
    while( 1 > 0 ){
        cout  << temp->data <<  "(" << temp->priority << ")" << "->";
        if(temp->next == NULL){
            cout << "NULL";
            return ;
        }
            
        temp = temp -> next;
    }
}

int main() {
   
    head = push( head , 3 ,3);
    head = push( head , 3 ,6);
 
    printing(head);

}
```











