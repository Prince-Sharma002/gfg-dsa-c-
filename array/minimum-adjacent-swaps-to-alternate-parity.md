```
Input: nums = [2,4,6,5,7]

Output: 3

Explanation:

Swapping 5 and 6, the array becomes [2,4,5,6,7]

Swapping 5 and 4, the array becomes [2,5,4,6,7]

Swapping 6 and 7, the array becomes [2,5,4,7,6]. The array is now a valid arrangement. Thus, the answer is 3.
```



```
int minSwaps(vector<int>& nums) {
    int n = nums.size();
    vector<int> evenIdx, oddIdx;
    
    for (int i = 0; i < n; ++i) {
        if (nums[i] % 2 == 0)
            evenIdx.push_back(i);
        else
            oddIdx.push_back(i);
    }
    
    int evenCount = evenIdx.size();
    int oddCount = oddIdx.size();
    
    if (abs(evenCount - oddCount) > 1) 
        return -1;

    int res = INT_MAX;
    
    // Try starting with even
    if (evenCount >= oddCount) {
        int swaps = 0;
        for (int i = 0; i < evenIdx.size(); ++i) {
            swaps += abs(evenIdx[i] - 2 * i);
        }
        res = min(res, swaps);
    }

    // Try starting with odd
    if (oddCount >= evenCount) {
        int swaps = 0;
        for (int i = 0; i < oddIdx.size(); ++i) {
            swaps += abs(oddIdx[i] - 2 * i);
        }
        res = min(res, swaps);
    }

    return res;
}
```
