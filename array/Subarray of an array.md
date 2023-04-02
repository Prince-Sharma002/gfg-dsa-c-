# Subarray of an array

## Approach 1 - Brute Force
```
#include <iostream>
#include <bits/stdc++.h>
#include <array>
using namespace std;

int main() {
    int arr[] = {1,2,3,4};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    for(int i=0 ; i<n ; i++ ){
        for( int j=i ; j<n ; j++ ){
            for(int k=i ; k <= j ; k++){
                cout << arr[k];
            }
            cout<< endl;
        }
    }
    

}

```

## Approach 2 - Recursion

```
#include <iostream>
#include <bits/stdc++.h>
#include <array>
using namespace std;

void subarray(int arr[] , int n , int s , int e){
    if(s >= n)
        return;
    
    if(e > n ){
        s++;
        e = s;
    }
    
    for(int i=s ; i<=e ; i++ ){
        cout<< arr[i];
    }
    cout<<endl;
    subarray(arr, n , s , e+1);
    
}

int main() {
    int arr[] = {1,2,3,4};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    
    subarray(arr, n-1 , 0  , 0);

}
```
