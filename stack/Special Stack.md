# Special Stack

```
void push(stack<int>& s, int a){
    s.push(a);
}

bool isFull(stack<int>& s,int n){
	if( s.size() == n )
	    return true;
	return false;
}

bool isEmpty(stack<int>& s){
	if( s.size() == 0 )
	    return true;
	 return false;
}

int pop(stack<int>& s){
	int d = s.top();
	if( s.top() == NULL )
	    return -1;
	s.pop();
	return d;
}

void solve( stack<int>& s , int* mini ) 
{
    if( s.empty() )
        return ;
    int ele = s.top();
    s.pop();
    *mini = min( *mini , ele );
    
    solve( s , mini );
    s.push( ele );
    
}


int getMin(stack<int>& s){
    int mini = 100000;
    solve( s , &mini);
    
    return mini;
}
```
