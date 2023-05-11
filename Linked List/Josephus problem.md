# Josephus problem

### Example
```
Input:
n = 5 k = 3
Output: 4
Explanation: There are 5 persons so 
skipping 2 person i.e 3rd person will 
be killed. Thus the safe position is 4.
```

### Code
``` 
int josephus(int n, int k)
{
    int i = 1;
    int ans = 0;
    while(i<=n){
        ans = (ans + k)%i;
        i++;
    }
    return ans+1;
}
```











