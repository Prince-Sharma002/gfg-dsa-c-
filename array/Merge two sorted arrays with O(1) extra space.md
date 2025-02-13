# Merge two sorted arrays with O(1) extra space

```
void sort( long long arr2[] , int m ){
    int i = 0;
    while( arr2[i] > arr2[i+1] && i+1 <= m-1 ){
        swap(arr2[i] , arr2[i+1]);
        i++;
    }
} 
                  
          
void merge(long long arr1[], long long arr2[], int n, int m) 
{ 
    int temp;
    for( int i=0 ; i<n ; i++ ){
    
        if(arr1[i] < arr2[0] ){
            continue;
        }
        else{
            temp = arr1[i];
            arr1[i] = arr2[0];
            arr2[0] = temp;
            sort( arr2 , m );
        }
    }
} 
```

```
int main() {
    // TC - O((n+m) log(n+m))
    // Input: ar1[] = {1, 5, 9, 10, 15, 20}, ar2[] = {2, 3, 8, 13}
    // Output: ar1[] = {1, 2, 3, 5, 8, 9}, ar2[] = {10, 13, 15, 20}

    int arr1[] = {1, 3, 5 ,7};
    int arr2[] = {0 ,2, 6, 8 , 9 };
    int n = sizeof(arr1)/sizeof(arr1[0]);
    int m = sizeof(arr2)/sizeof(arr2[0]);
    
    int i=0 ; int j=0 ; int k=n-1;
    while( i <= k && j < m  ){
        if( arr1[i] < arr2[j] )
            i++;
        else
            swap( arr1[k--] , arr2[j++] );
    }
    
    // sort array
    sort( arr1 , arr1 + n );
    sort( arr2 , arr2 + m );

}
```

## Approach 2 ( two pointers )
```
    void mergeArrays(vector<int>& a, vector<int>& b) {
        int n = a.size();
        int m = b.size();
        
        int left = n-1; // 
        int right = 0;
        
        while( left >= 0 && right <= m-1 ){
            if( a[left] > b[right] )
            {
                swap( a[left] , b[right] );
                left--;
                right++;
            }
            else
                break;
        }
        
        sort( a.begin() , a.end() );
        sort( b.begin() , b.end() );
        
    }
```











