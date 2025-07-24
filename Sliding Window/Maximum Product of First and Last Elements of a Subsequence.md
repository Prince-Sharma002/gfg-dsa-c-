```
Example 1:

Input: nums = [-1,-9,2,3,-2,-3,1], m = 1

Output: 81

Explanation:

The subsequence [-9] has the largest product of the first and last elements: -9 * -9 = 81. Therefore, the answer is 81.

Example 2:

Input: nums = [1,3,-5,5,6,-4], m = 3

Output: 20

Explanation:

The subsequence [-5, 6, -4] has the largest product of the first and last elements.

Example 3:

Input: nums = [2,-1,2,-6,5,2,-5,7], m = 2

Output: 35

Explanation:

The subsequence [5, 7] has the largest product of the first and last elements.
```



```
long long maximumProduct(vector<int>& nums, int m) {
    int n = nums.size();
    if (m <= 0 || m > n) return 0;          // guard, optional

    // m == 1: pick any single element; product = x * x, maximize it
    if (m == 1) {
        long long best = LLONG_MIN;
        for (int x : nums) best = max(best, 1LL * x * x);
        return best;
    }

    vector<int> prefmax(n), prefmin(n);
    prefmax[0] = prefmin[0] = nums[0];
    for( int i=1 ; i<n ; i++ ){
        prefmax[i] = max( prefmax[i-1], nums[i] );
        prefmin[i] = min( prefmin[i-1], nums[i] );
    }

    long long ans = LLONG_MIN;
    for( int j=m-1 ; j<n ; j++ ){
        int upto = j - m +1;
        long long a = 1LL * nums[j] * prefmax[upto];
        long long b = 1LL * nums[j] * prefmin[upto];

        ans = max( ans , max(a,b) );
    }

    return ans;
    
}
```
