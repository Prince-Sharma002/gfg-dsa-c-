# Unique Bst's

```

int solve(int N, vector<int>& dp) {
    // BASE CASE
    if (N <= 1) {
        return 1;
    }
    
    // RETURN SAVED VALUE
    if (dp[N] != -1) {
        return dp[N];
    }

    int ans = 0;
    
    // LOOP OF ROOT NODES
    for (int i = 1; i <= N; i++) {
        ans += solve(i - 1, dp) * solve(N - i, dp);
    }
    dp[N] = ans;
    return dp[N];
}

int solveTab( int N ){
    vector<int> dp(N+1 , 0);
    
    // BASE CONDITION VALUE
    dp[0] = 1 ; dp[1] = 1;
    
    // Number of Nodes
    for( int i=2 ; i<=N ; i++ ){
        // root node same as in approach 1 for loop( Root Node )
        for( int j=1 ; j<=i ; j++ ){
            dp[i] += dp[j-1]*dp[i-j];
        }
    }
    
    return dp[N];
    
}


int numTrees(int N) {
    vector<int> dp(N + 1, -1);
    return solveTab(N);
}
```
