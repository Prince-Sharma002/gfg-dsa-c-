# Reversing an array

## Approach 1 (Swaping)
```
#include <iostream>
#include <bits/stdc++.h>
#include <array>
using namespace std;

void printarr(int arr[] , int n){
    
       for( int i=0 ; i<n ; i++ ){
        cout<<arr[i];
    } 
}

int main() {
    int arr[] = {1,2,3,4,5,6};
    int n = sizeof(arr)/sizeof(arr[0]);
    int temp;
    
    // reversing array
    for( int i=0 ; i<n/2 ; i++ ){
        temp = arr[n-1-i];
        arr[n-1-i] = arr[i];
        arr[i] = temp;
    }
    
    printarr(arr , n);

}
```

## Approach 2 (Recursion)
```
#include <iostream>
#include <bits/stdc++.h>
#include <array>
using namespace std;

void printarr(int arr[] , int n){
    
       for( int i=0 ; i<n ; i++ ){
        cout<<arr[i];
    } 
}

void reverse(int arr[] , int a , int b ){
    if( a >= b ){
        return;
    }
    
    swap(arr[a] , arr[b]);
    reverse( arr , a+1 , b-1 );
    
}

int main() {
    int arr[] = {1,2,3,4,5};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    // reversing array
    reverse( arr , 0 , n-1);
    
    
    printarr(arr , n);

}
```