```
Input:
N = 4
arr[] = {geeksforgeeks, geeks, geek,
         geezer}
Output: gee
```

```
    string longestCommonPrefix (string arr[], int N)
    {
       string ans = arr[0];
       for( int i=1 ; i<N ; i++ ){
           string str = arr[i];
           string temp = "";
           for( int j=0 ; j<str.length() ; j++ ){
               if( ans[j] == str[j] )
                    temp = temp + str[j];
               else{
                    ans = temp;
                    break;
               }
               
                if( j == (str.length() - 1) ){
                    ans = temp;
                    break ;
               }
           }
           
       }
       
       if( ans == "")
        return "-1";
       return ans;
    }
```
