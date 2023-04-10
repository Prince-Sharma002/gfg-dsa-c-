# Print a Distinct Digit Array


## Find All distinct elements in an array 
```
int main() {
    
    int arr[] = { 131 , 11 , 48 };
    int n = sizeof(arr) / sizeof(arr[0]);
    vector<int> ans;
    unordered_map<int ,int> umap;
    int rem;
    for( int i=0 ; i<n ; i++ ){
        int n = arr[i];
        while(n>0){
            rem = n%10;
            umap[rem]++;
            n = n/10;
        }
    }
    
    // printing ditinct numbers
    for( auto x : umap ){
        cout<< x.first << endl;
    }
        
}

```







