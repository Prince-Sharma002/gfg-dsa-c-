# Intersection Point in Y Shaped Linked Lists

### Example
```
Input:
LinkList1 = 3->6->9->common
LinkList2 = 10->common
common = 15->30->NULL
Output: 15
```

### Code
``` 
int intersect( Node* head1 , Node* head2 , int c1 , int c2 ){
    Node* temp1 = head1;
    Node* temp2 = head2;
    int a = 0;
    while( c1-c2 > a ){
        temp1 = temp1->next;
        a++;
    }
    while(  temp1 != NULL || temp2 != NULL ){
        if(temp1 == temp2 )
            return temp1->data;
        temp1 = temp1->next;
        temp2 = temp2->next;
    }
    return -1;
    
}

int intersectPoint(Node* head1, Node* head2)
{
    Node* temp1 = head1;
    Node* temp2 = head2;
    int c1 = 0; int c2 = 0;
    
    while( temp1 != NULL ){
        temp1 = temp1->next;
        c1++;
    }
    while( temp2 != NULL ){
        temp2 = temp2->next;
        c2++;
    }
    
    if( c1 > c2 ){
        return intersect( head1 , head2 , c1 ,c2 );
    }
    else{
        return intersect( head2 , head1 , c2 ,c1 );
    }
  
}
```











