# Selection Sort

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

void selectionSort(int arr[] , int n ){
    int min;
    for(int i=0 ; i<n-1 ; i++ ){
        min = i;
        for( int j=i+1 ; j<n ; j++ ){
            if(arr[j] < arr[min] )
                min = j;
        }
        swap(arr[min] , arr[i]);
    }
}



int main() {
    int arr[] = {3,2,6,8,4,1,9};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    selectionSort(arr,n);
    
    printarr(arr , n);

}
```
