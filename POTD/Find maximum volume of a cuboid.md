```
Input: perimeter = 22, area = 15
Output: 3.02
```

```
    double maxVolume(double P, double A) {
        // calculate length
    double l = (P - sqrt(P * P - 24 * A)) / 12;
 
    // calculate volume
    double V = l * (A / 2 - l * (P / 4 - l));
 
    // return result
    return V;
 
         
    }
```
