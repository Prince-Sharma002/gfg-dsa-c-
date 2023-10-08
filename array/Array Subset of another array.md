# Array Subset of another array

```
string isSubset(int a1[], int a2[], int n, int m) {
    
    sort( a1 , a1+n );
    sort( a2 , a2+m );
    
    int ind = 0;
    int i=0;
    
    if( n < m )
        return "No";
    
    while( i< n && ind < m  ){
        if( a1[i] == a2[ind] ){
            i++; ind++;
            continue;
        }
        else if( a1[i] < a2[ind] )
            i++;
        else return "No";
    }
    
    return "Yes";
}
```
