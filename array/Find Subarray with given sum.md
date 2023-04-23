# Find Subarray with given sum

```
// Input: arr[] = {1, 4, 20, 3, 10, 5}, sum = 33
// Output: Sum found between indexes 2 and 4
// TC - 0(N)
    vector<int> subarraySum(vector<int>arr, int n, long long s)
    {
        
    int i=0 ; int j=0 ; int sum = arr[0];
    vector<int> ans;
    while(i < n){
        while( sum > s  && j <= i - 1){
            sum = sum - arr[j];
            j++;
        }
        if( sum == s ){
            i = i+1;
            j = j+1;
            vector<int> ans;
            ans.push_back(j);
            ans.push_back(i);
            return ans;
        }
        if( i < n ){
            i++;
            sum = sum + arr[i];
        }

    }

    ans.push_back(-1);
    return ans;

    }
```











