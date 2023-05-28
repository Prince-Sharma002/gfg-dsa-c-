# Closing bracket index
### Example
```
Input:
S = "[ABC[23]][89]"
pos = 0
Output: 8
Explanation: [ABC[23]][89]
The closing bracket corresponding to the
opening bracket at index 0 is at index 8.
```

### Code
```
int closing (string s, int pos)
{
        int a=1;
    	for(int i=pos+1 ; i<s.size() ; i++ ){
    	    if(s[i] == '[')
    	        a++;
    	    else if( s[i] == ']' )
    	        a--;
    	    
    	    if( a == 0 )
    	        return i;
    	    
    	}
    	
    	return -1;
}
```











