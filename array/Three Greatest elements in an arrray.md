# Three Greatest elements in an arrray

```
#include <iostream>
using namespace std;

int main() {
	int a[] = {10, 4, 3, 50, 23, 90};
	int n = sizeof(a)/sizeof(a[0]);
    int max1=0 , max2=0 , max3=0;
    for(int i=0; i<n ; i++ ){
        if(a[i] < max1 ){
            if(a[i] < max2 ){
                if( a[i] < max3 )
                    continue;
                else
                    max3 = a[i];
            }
            else{
                max3 = max2;
                max2 = a[i];
            }
        }
        else{
            max3 = max2;
            max2 = max1;
            max1 = a[i];
        }
        
    }
    
    cout<< "max1 : " << max1 <<endl;
    cout<< "max2 : " << max2 <<endl;
    cout<< "max3 : " << max3 <<endl;
    
}
```


