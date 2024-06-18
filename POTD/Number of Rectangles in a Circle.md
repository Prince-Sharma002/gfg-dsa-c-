```
Input: r=2
Output: 8
Explanation: The 8 possible rectangles are 
(1x1)(1x2)(1x3)(2x1)(2x2)(2x3)(3x1)(3x2).
```

```
    int rectanglesInCircle(int r) {
        int rectangle = 0;
        
        int dia = 2*r;
        
        int diaSqr = dia*dia;
        
        for( int i=1 ; i<2*r ; i++ ){
            for( int j=1 ; j<2*r ; j++ ){
                
                int diagonal = i*i + j*j;
                if( diaSqr >= diagonal )
                    rectangle++ ;
            } 
        }
        return rectangle;
    }
```
