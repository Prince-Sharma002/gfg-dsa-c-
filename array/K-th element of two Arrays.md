```
Input:
arr1[] = {2, 3, 6, 7, 9}
arr2[] = {1, 4, 8, 10}
k = 5
Output:
6
```

```
    int kthElement(int arr1[], int arr2[], int n, int m, int k)
    {
        int i=0;
        int a = 0;
        int b = 0;
        int ele;
        while( a < n && b < m ){
            if( arr1[a] < arr2[b] ){
                ele = arr1[a];
                a++;
            }
            else{
                ele = arr2[b];
                b++;
            }
            
            i++;
            if( i == k )
                return ele;
            
        }
        
        while( a < n ){
            ele = arr1[a];
            a++;
            i++;
            if( i == k )
                return ele;
        }
        
        while( b < m ){
            ele = arr2[b];
            b++;
            i++;
            if( i == k )
                return ele;
        }
        
    }
```
