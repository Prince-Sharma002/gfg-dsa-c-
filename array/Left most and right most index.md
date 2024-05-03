```
    pair<long,long> indexes(vector<long long> v, long long x)
    {
        long left = -1 ; 
        long right = -1;
        
        int s = 0 ; 
        int e =  v.size() - 1;
        
        // Binary search to find left index
        while (s <= e) {
            int mid = (s + e) / 2;
            if (v[mid] == x) {
                left = mid;
                e = mid - 1; // Move to the left half
            } else if (v[mid] < x)
                s = mid + 1;
            else
                e = mid - 1;
        }
            
        s = 0; e = v.size() - 1;
        
         // Binary search to find right index
        while (s <= e) {
            int mid = (s + e) / 2;
            if (v[mid] == x) {
                right = mid;
                s = mid + 1; // Move to the right half
            } else if (v[mid] < x)
                s = mid + 1;
            else
                e = mid - 1;
        }
        
        return make_pair(left, right);
        
    }
```
