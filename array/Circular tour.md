```
Input:
N = 4
Petrol = 4 6 7 4
Distance = 6 5 3 5
Output: 1
```

```
    int tour(petrolPump p[],int n)
    {
        
       // check if the total petrol is greater than total distance  
       int pSum = 0 , dSum = 0;
       for( int i=0 ; i<n ; i++ ){
           pSum += p[i].petrol;
           dSum += p[i].distance;
       }
       
       // if total petrol is lesser than total distance then simply return -1 4
       //  else circular tour is possible  
       if( pSum < dSum )
            return -1;
        
        
        int f=0 , r = 0 , balance = 0; 
        int step = 0;
        
        
        // loop until one complete circular tour 
        while( step < n -1  ){
            
          
            int diff = p[r].petrol - p[r].distance;
            
            balance  += diff;
            
            // if balance if lesser than 0 increase both front and rear by 1
            // balance again 0 
            // step again to 0
            if( balance < 0 ){
                r++;
                f = r;
                balance = 0;
                step = 0;
            }   
            // else increase step and rear 
            else{
                step++;
                r++;
                // if r reaches end 
                if( r == n )    
                    r = 0;
            }
            
        }
        
        // return f
        if( balance )
            return f;
            
    }
```
