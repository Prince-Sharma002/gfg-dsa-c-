# Alternate positive and negative numbers


## order not maintain
```
// Arr[] = { 9, 4, -2, -1, 5, 0, -5, -3, 2 }
//Output: 9 -2 4 -1 5 -5 0 -3 2

int main() {
    
    int arr[] = { 1,2,3,4,-5,-6,-7,-8 };
    int n = sizeof(arr)/sizeof(arr[0]);
    int i=0; int j=n-1;
    
    // place all negative elements on right 
    while( i <= j ){
        if( arr[i] >= 0 ){
            i++;
            continue;
        }
        if( arr[i] < 0 && arr[j] >= 0 ){
            swap( arr[i++] ,  arr[j--] );
        }
        else
            j--;
    }
    
    i = 0 ; j = j+1 ;
    
    int mid = ( 0 + n )/2;

    // if negative numbers are greater than positive
    if( mid >= j ){
        while( i < n ){
            if( i%2 == 0 && arr[i] < 0 )
                break;
            
            if( i%2 == 0  && arr[i] >= 0 ){
                i++;
                continue;
            }
            else{
                swap( arr[i] , arr[j] );
                i++; j++;
                continue;
            }            
        }

    }
    // if positive number are greater than negative
    else{
        while( i < n-1){
            if( i%2 == 0  && arr[i] >= 0 ){
                i++;
                continue;
            }
            else{
                if( j < n ){
                    swap( arr[i] , arr[j] );
                    i++; j++;
                    continue;                
                }
                else{
                    i++;
                }

            } 

        }
    }

    
    // printing array
    for( int i=0 ; i<n ; i++ ){
        cout << arr[i] << " ";
    }
    
}
```


```
vector<int> posarr;
vector<int> negarr;

for(int i=0; i<n ; i++ ){
    if( arr[i] >= 0)
        posarr.push_back(arr[i]);
    else
        negarr.push_back(arr[i]);
}

int posIndex=0;
int negIndex=0;
for( int i=0 ; i<n ; i++ ){
    if( i%2 == 0 ){
        if(posIndex < posarr.size() )
            arr[i] = posarr[posIndex++];
        else
            arr[i] = negarr[negIndex++];
    }
    else{
        if( negIndex < negarr.size() )
            arr[i] = negarr[negIndex++];
        else
            arr[i] = posarr[posIndex++];
    }
}

// timeComplexity - 0(n)
// spaceComplexity - 0(n)
```

### Order maintain

```
	void rearrange(int arr[], int n) {
        vector<int> posArr;
        vector<int> negArr;
	    for( int i=0 ; i<n ; i++ ){
	        if( arr[i] >= 0 )
	            posArr.push_back( arr[i] );
	        else
	            negArr.push_back( arr[i] );
	    }
	    
	    int i ; int j=0 ; int k=0;
	    int flag = 0;
	    for( i=0 ; i<n ; i++ ){
	        if( j >= posArr.size() || k >= negArr.size() )
	        {
	            flag = 1;
	            break;
	        }
	        
	        if( i%2 == 0){
	            arr[i] = posArr[j++];
	        }
	        else
	            arr[i] = negArr[k++];
	        
	    }
	    
	    if( flag  == 1 ){
	        if( j < posArr.size() ){
	            while( j < posArr.size() ){
	                arr[i] = posArr[j]; 
	                i++; j++;
	            }
	        }
	        else{
	            while( k < negArr.size() ){
	                arr[i] = negArr[k]; 
	                i++; k++;
	            }	           
	        }
	    } 
	    
	}
```










