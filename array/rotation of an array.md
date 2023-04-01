# Rotation of an array

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

void rotation(int arr[] , int n ){
    int a = 1 , temp = arr[0] , temp2 ;
    
    
    // condition for last element
    for( int i=1 ; i<= n ; i++){
        if(i==n){
            arr[0] = arr[i]; 
        }
        


    temp2 = arr[i];
    arr[i] = temp;
    temp = temp2;
         
        
        
    }
}

int main() {
    int arr[] = {1,2,3,4,5};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    // reversing array
    rotation(arr , n-1 );
    
    
    printarr(arr , n);

}
```
