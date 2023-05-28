# Maximum Difference
### Example
```
Input  : arr[] = {2, 4, 8, 7, 7, 9, 3}
Output : 4
Left smaller   LS[] = {0, 2, 4, 4, 4, 7, 2}
Right smaller  RS[] = {0, 3, 7, 3, 3, 3, 0}
Maximum Diff of abs(LS[i] - RS[i]) = 7 - 3 = 4 
```

### Code
```
void SmallerElementIndex(int n, int a[] , int larr[] , int rarr[]){
        stack<int> st;
        stack<int> st2;
        for( int i=0 , j=n-1 ; i<n , j>=0 ; i++ , j--){

                // larray index finding
                while( !st.empty() && st.top() >= a[i] )
                    st.pop();
                
                if( st.empty() ){
                    st.push( a[i] );
                    larr[i] = 0;
                }
                else{
                    larr[i] = st.top();
                    st.push( a[i] );               
                }

                
                // rarray index finding
                while( !st2.empty() && st2.top() >= a[j] )
                    st2.pop();
                    
                if( st2.empty() ){
                    st2.push( a[j]  );
                    rarr[j] = 0;
                }
                else{
                    rarr[j] = st2.top();
                    st2.push( a[j] );                   
                }


        }
         
}
    int findMaxDiff(int A[], int n)
    {
       int larr[n];
        int rarr[n];
    SmallerElementIndex(n , A , larr , rarr);
    
    int max = -1;
    
    for( int i=0 ; i<n ; i++ ){
        if( abs(rarr[i] - larr[i]) > max )
            max = abs(rarr[i] - larr[i]);
    }
    
    return abs(max);
                
    }
```











