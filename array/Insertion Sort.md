# Insertion Sort

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

void insertionSort(int arr[] , int n ){
    
    int d,temp;
    for(int i=1 ; i<n ; i++ ){
        temp = arr[i];
        d = i-1;
        while( d>=0 && temp < arr[d] ){
            arr[d+1] = arr[d];
            d--;
        }
        arr[d+1] = temp;
    }
    
}


int main() {
    int arr[] = {3,2,6,8,4,1,9};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    insertionSort(arr,n);
    
    printarr(arr , n);

}
```
