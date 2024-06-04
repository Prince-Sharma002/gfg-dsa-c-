```
void toBinary(int N){
    
    int i=0;
    string s = "";
    if(N == 0) {
        cout << '0';
        return;
    }

 
    while (N > 0) {
        int rem = N%2;
        if( rem == 0 )
            s = '0' + s;
        else 
            s = '1' + s;
        N = N/2;
    }

    cout << s;

        
}
```
