# Tower Of Hanoi

```
    void solve( long long *ans , int N , int from , int to , int aux ){
        if( N == 0 )
            return ;
        
        solve( ans , N-1 , from , aux , to );
        printf( "move disk %d from rod %d to rod %d\n" , N , from, to);
        *ans += 1;
        solve( ans , N-1 , aux , to , from );
        
    }
    
    long long toh(  int N, int from, int to, int aux) {
        long long ans=0;
        solve( &ans , N , from , to , aux );
        return ans;
    }

```
