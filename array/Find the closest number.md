```
Input: 
n = 4
k = 4
arr[] = {1, 3, 6, 7}
Output: 
3
```


```
    int findClosest( int n, int k,int arr[]) 
    { 
        int s = 0 ; int e = n-1;
        
        int mid = -1;
        
        while( s <= e ){
            mid = (s+e)/2;
            
            if( arr[mid] == k )
                break;
            else if( arr[mid] < k )
                s = mid+1;
            else 
                e = mid-1;
        }
        
        
        int first , sec;
        
        if( arr[mid] == k )
        {
            return arr[mid];
        }
        else if( arr[mid] < k ){
            first = k - arr[mid];
            sec = arr[mid+1] - k;
        }
        else{
            first = k - arr[mid-1];
            sec = arr[mid] - k;
        }
        
        if( first >= sec )
            return k + sec;
        return k - first;
         
    } 
```
