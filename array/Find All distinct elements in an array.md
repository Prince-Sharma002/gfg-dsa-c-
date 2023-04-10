# sort the array into a wave-like array


## Find All distinct elements in an array 
```
int main() {
    
    int arr[] = { 12, 10, 9, 45, 2, 10, 10, 45 };
    int n = sizeof(arr) / sizeof(arr[0]);
    
    unordered_map<int , int> umap;
    for( int i ; i<n ; i++ ){
        umap[arr[i]]++;
    }
    
     
    for( auto x : umap ){
        if(x.second == 1)
            cout<< x.first <<endl;
        else
            break;
    }
    
        
}

```







