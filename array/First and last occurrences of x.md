```
n=9, x=5
arr[] = { 1, 3, 5, 5, 5, 5, 67, 123, 125 }
Output:  
2 5
```

```
    vector<int> find(int arr[], int n , int x )
    {
     int s = 0 , e = n-1;
    int startInd = -1, endInd = -1;
    
    while( s <= e  ){
        int mid = (s+e)/2;

        if( arr[mid] < x )
            s = mid+1;
        else if( arr[mid] > x )
            e = mid-1;
        else{
            startInd = mid;
            e = mid-1;
        }
        
    }

    s = 0 ; e = n-1;
    while( s <= e  ){
        int mid = (s+e)/2;
        
        if( arr[mid] < x )
            s = mid+1;
        else if( arr[mid] > x )
            e = mid-1;
        else
        {
            endInd = mid;
            s = mid+1;
        }
        
        
    }
    
    vector<int> ans;
    ans.push_back(startInd);
    ans.push_back(endInd);
    
    return ans;

    }
```
