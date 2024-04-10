```
Input:
x = 5
Output: 2
Explanation: Since, 5 is not a perfect 
square, floor of square_root of 5 is 2.
```

```
    long long int floorSqrt(long long int x) 
    {
        int ans = 0;
        long long i = 0;
        
        while( i*i <= x ){
            if( i*i == x) 
                return i;
            
            i++;
            
        }
        
        return i-1;
        
    }
```
