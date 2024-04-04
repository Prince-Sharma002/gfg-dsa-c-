```
There are n stairs, a person standing at the bottom wants to reach the top. The person can climb either 1 stair or 2 stairs at a time. Count the number of ways, the person can reach the top (order does matter).
```

```
int countWays(int n) {
  
    int dp[n + 1];
    int a = 1 , b = 1 , temp;

    for (int i = 2; i <= n; ++i) {
        temp = (a+b)%1000000007;
        
        a = b;
        b = temp;
    }

    return b; 
         
  }
```
