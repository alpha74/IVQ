## Credgenics - Problem 1
#### Aman Kumar

### Problem Statement

Given an m x n matrix, set each element of that row and column to 0 if the current element is 0.

#### Example

- Input
    ```
    0 0 5
    1 4 3
    9 7 8
    ```

- Output:
    ```
    0 0 0
    0 0 3
    0 0 8
    ```

### Versions:
1. No constraints
    - Can be done easily
  
2. Use no extra space
    - See code.
    - Trick is to set each row's and column's first element as 0 if any element in the row or column is zero.
    - During printing, check if first element is 0, then print 0, else print the val at that index.
  
### Solution (for ver2):

```
// amanalphakumar

/*
	INSIGHT: 
		See code
*/

#include <bits/stdc++.h>

using namespace std ;

#define ll long long int
#define ff first
#define ss second
#define MOD 1000000007

#define FIO

void vader() ;

int main()
{
	#ifdef FIO
	ios_base::sync_with_stdio( 0 ) ;
	cin.tie(0) ;
	#endif
	
	int t =1  ;
	cin >> t; 
	
	while(t--) vader() ;
	
	return 0 ;
}

void vader()
{
	int n, m ;
	cin >> n >> m ;
	
	vector<vector<int>> mat ;
	
	for( int i = 0 ; i < n ; i++ )
	{
		vector<int> row ;
		
		for( int j = 0 ; j < m ; j++ )
		{
			int temp ;
			cin >> temp ;
			
			row.push_back( temp ) ;
		}
		mat.push_back( row ) ;
	}
	
	
	for( int i = 0 ; i < n ; i++ )
	{
		for( int j = 0 ; j < m ; j++ )
		{
			if( mat[i][j] == 0 )
			{
				// Set first element in height as 0
				mat[0][j] = 0 ;
				mat[i][0] = 0 ;
			}
		}
	}
	
	// Print 
	for( int i = 0 ; i < n ; i++ )
	{
		cout << "\n" ;
		for( int j = 0 ; j < m ; j++ )
		{
			if( mat[0][j] == 0 || mat[i][0] == 0 )
				cout << "0 " ;
			else
				cout << mat[i][j] << " " ;
		}
	}
	
}
```
