# Smallest subarray with sum greater than a given value

```
// arr[] = {1, 4, 45, 6, 0, 19}
//   x  =  51
// Output: 3
// TC - 0(N)
int smallestSubWithSum(int arr[], int n, int x)
{

    int i=0 ; int j=0 ; int sum = arr[0];
    int d = INT_MAX;
    while(i < n){
        while( sum > x && j<= i){
            if( d > i - j )
                d = i - j;
            sum = sum - arr[j];
            j++;
        }
        if( i < n ){
            i++;
            sum = sum + arr[i];
        }

    }
    if( d == INT_MAX ){
        return 0;
    }
    else
        return d+1;
}
```











