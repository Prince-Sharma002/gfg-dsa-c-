```
Input: arr[] = [1, 2, 3, 3, 5], target =7
Output: [[1, 3, 3], [2, 5]]
Explanation: Total number of possible combinations are 2.
```


```
#include <bits/stdc++.h>
using namespace std;

void solve(int ind, int sum, int target, vector<int> &arr, vector<vector<int>> &ans, vector<int> &ds) {
    if (sum == target) {
        ans.push_back(ds);
        return;
    }
    
    for (int i = ind; i < arr.size(); i++) {
        if (i > ind && arr[i] == arr[i - 1]) continue; // Skip duplicates
        if (sum + arr[i] > target) break; // Stop if sum exceeds target
        
        ds.push_back(arr[i]);
        solve(i + 1, sum + arr[i], target, arr, ans, ds);
        ds.pop_back();
    }
}

vector<vector<int>> uniqueCombinations(vector<int> &arr, int target) {
    sort(arr.begin(), arr.end()); // Sort to handle duplicates
    vector<int> ds;
    vector<vector<int>> ans;
    solve(0, 0, target, arr, ans, ds);
    return ans;
}

int main() {
    vector<int> arr = {10, 1, 2, 7, 6, 5};
    int target = 8;
    vector<vector<int>> result = uniqueCombinations(arr, target);
    
    for (auto &combination : result) {
        for (int num : combination) {
            cout << num << " ";
        }
        cout << endl;
    }
    
    return 0;
}

```
