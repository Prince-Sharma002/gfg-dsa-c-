# Leaders in an array


```
//Function to find the leaders in the array.
vector<int> leaders(int a[], int n){
    
    // if there are too long input use long long
    // evrywhere where int used
    
    vector<int> ans;
    long long max = a[n-1];
    ans.push_back(max);
    for( long long i=n-2 ; i>=0 ; i-- ){
        if(a[i] >= max ){
            max = a[i];
            ans.push_back(max);
        }
        
    }
    reverse(ans.begin(), ans.end());
    
    return ans;
    
}

```







