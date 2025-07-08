```
Input: arr[] = [2, 3]
Output: [ad, ae, af, bd, be, bf, cd, ce, cf]
Explanation: When we press 2, 3 total possible words are 3 x 3 = 9.
```

```
void solve(int i, vector<int>& arr, vector<string>& phoneMap, vector<string>& ans, string& path) {
    
    // Base case: if we have formed a word of size equal to digits
    if (i == arr.size()) {
        ans.push_back(path);
        return;
    }

    // Get letters corresponding to current digit
    string letters = phoneMap[arr[i]];

    for (char ch : letters) {
        path.push_back(ch);            // Choose
        solve(i + 1, arr, phoneMap, ans, path);  // Explore
        path.pop_back();               // Un-choose (backtrack)
    }
}

vector<string> possibleWords(vector<int>& arr) {
    vector<string> ans;
    string path = "";

    vector<string> phoneMap = {
        "",     // 0
        "",     // 1
        "abc",  // 2
        "def",  // 3
        "ghi",  // 4
        "jkl",  // 5
        "mno",  // 6
        "pqrs", // 7
        "tuv",  // 8
        "wxyz"  // 9
    };
    
    vector<int> newarr;
    for( int i=0 ; i<arr.size() ; i++ ){
        int ele = arr[i];
        if( ele == 1 || ele == 0 ){
            continue;
        }
        
        newarr.push_back( ele );
    }

    if (!arr.empty())
        solve(0, newarr, phoneMap, ans, path);

    return ans;
}
```
