## Airveda - Problem 2
#### Aman Kumar

### Problem Statement

Given two strings, find if they are anagrams or not.

#### Example

- Input
    ```
    str1 = "aabbcc"
    str2 = "bbccaa"
    ```

- Output:
    ```
    Yes
    ```

### Solution Approaches :
1. Can be solved by storing counts of each char in two strings in separate variables(maps), using maps. 
Then just check if frequency of each char in first map is equal to second and same for map2.



### Solution (Approach 1)
```
#include <bits/stdc++.h>

using namespace std;

bool isAnagram( string s1, string s2 )
{
    map<char,int> m1, m2 ;
    
    // Get freq of chars from s1 and s2
    for( int i = 0 ; i < s1.length() ; i++ )
    {
        m1[ s1[i] ]++ ;
    }
    
    for( int i = 0 ; i < s2.length() ; i++ )
    {
        m2[ s2[i] ]++ ;
    }
    
    bool ret = true ;
    
    // Compare frequencies
    for( int i = 0 ; i < s1.length() && ret == true ; i++ )
    {
        if( m1[ s1[i] ] != m2[ s1[i]] )
            ret = false ;
    }
    
    if( ret )
    {
        for( int i = 0 ; i < s2.length() && ret == true ; i++ )
        {
            if( m1[ s2[i] ] != m2[ s2[i] ] )
                ret = false ;
        }
    }
    
    return ret ;
}

int main()
{
   cout << isAnagram( "aabbcc", "aabbcc") ;
}


```
