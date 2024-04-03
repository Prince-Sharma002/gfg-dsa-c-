# Minimum number of jumps
```
Input:
N = 5, S = 12
A[] = {1,2,3,7,5}
Output: 2 4
Explanation: The sum of elements 
from 2nd position to 4th position 
is 12.
```
### code
```
    vector<int> subarraySum(vector<int>arr, int n, long long s)
    {
        int i=0 ,  sum = 0 ; 
        vector<int> ans;
        
        for( i = 0 ; i <n ; i++ ){
            if( arr[i] == s )
            {
                ans.push_back(i+1);
                ans.push_back(i+1);
                return ans;
            }
        }
        
        i = 0;  
        int j = 1;
        
        sum = arr[i] + arr[j];
        while( j < n  && i < n  && i <= j ){
            if( sum == s ){
                ans.push_back(i+1);
                ans.push_back(j+1);
                return ans;
            }
            else if( sum < s ){
                j++; 
                sum += arr[j];
            }
            else if( sum > s ){
                sum -= arr[i];
                i++;
            }
        }
        
        ans.push_back(-1);
        return ans;
    }
```
