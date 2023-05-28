# Maximum Rectangular Area in a Histogram
### Example
```
Input:
N = 7
arr[] = {6,2,5,4,5,1,6}
Output: 12
```

### Code
```
void SmallerElementIndex(int n, long long a[] , long long larr[] , long long rarr[]){
        stack<pair<long long , long long>> st;
        stack<pair<long long , long long>> st2;
        for( long long i=0 , j=n-1 ; i<n , j>=0 ; i++ , j--){

                // larray index finding
                while( !st.empty() && st.top().first > a[i] )
                    st.pop();
                
                if( st.empty() ){
                    st.push( make_pair(a[i] , i) );
                    larr[i] = -1;
                }
                else{
                    larr[i] = st.top().second;
                    st.push( make_pair(a[i] , i) );               
                }

                
                // rarray index finding
                while( !st2.empty() && st2.top().first > a[j] )
                    st2.pop();
                    
                if( st2.empty() ){
                    st2.push( make_pair(a[j] , j) );
                    rarr[j] = n;
                }
                else{
                    rarr[j] = st2.top().second;
                    st2.push( make_pair(a[j] , j) );                   
                }

        }
         
}

    long long getMaxArea(long long arr[], int n)
    {
        long long larr[n];
        long long rarr[n];
        SmallerElementIndex(n , arr , larr , rarr);
        
        long long max = INT_MIN;
        for( long long  i=0 ; i<n ; i++ ){
            if( ( (rarr[i]-1) - (larr[i] +1) + 1 )*arr[i] > max  )
                max = ( (rarr[i]-1) - (larr[i]+1) + 1 )*arr[i];
        }
        return max;    
    } 
```











