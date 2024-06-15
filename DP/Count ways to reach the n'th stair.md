```
long long solve(int n, long long dp[]) {
    if (n == 0)
        return 1;

    if (n < 0)
        return 0;

    if (dp[n] != -1) {
        return dp[n];
    }

    dp[n] = solve(n - 1, dp) + solve(n - 2, dp);
    return dp[n];
}

long long countWays(int n) {
    if (n <= 0) return 0;

    long long dp[n + 1];
    fill(dp, dp + n + 1, -1);
    return solve(n, dp)%1000000007;
}
```
