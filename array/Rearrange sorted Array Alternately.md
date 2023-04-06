# Rearrange sorted Array Alternately 


## Using Auxillary Space
```
int main() {
    
    int a[] = {10,20,30,40,50,60,70,80,90,100};
    
    int n = sizeof(a)/sizeof(a[0]);

    int a2[n];
    
    int x = 0 , y = n-1 ;
    for(int i=0 ; i<n ; i++ ){
        if(i%2 ==  0){
            a2[i] = a[y];
            y--;
        }
        else{
            a2[i] = a[x];
            x++;
        }
    } 

    // printing Array
    for( int i=0 ; i<n ; i++ ){
        cout<< a2[i] << endl;
    }
        
}

```

## If consecutive array( element differnce is 1 )
```
int main() {
    
    int a[] = {1,2,3,4,5,6,7};
    int n = sizeof(a)/sizeof(a[0]);
    
    int max = a[n-1];
    int min = a[0];
    
    for(int i=0 ; i<n ; i++ ){
        if( i%2 == 0){
            a[i] = max;
            max--;
        }
        else{
            a[i] = min;
            min++;
        }
    }

    
    for( int i=0 ; i<n ; i++ ){
        cout<< a[i] << endl;
    }
        
}
```






