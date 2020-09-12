## Airveda - Problem 1
#### Aman Kumar

### Problem Statement

Language: Python

Given two sentences as strings, print the words which are not present in both strings.

#### Example

- Input
    ```
    str1 = "This is not good"
    str2 = "This is very good"
    ```

- Output:
    ```
    not
    very
    ```

### Solution Approaches :
1. It can be solved using `dict`
2. Can be improved further using Python in-built `set`



### Solution (Approach 1)
```
str1 = "This is not good"
str2 = "This is very good"

# Split the strings on space
str1 = str1.split( " " )
str2 = str2.split( " " )

# Create dict of both strings
words_str1 = {}
words_str2 = {}

# Iterate and store words in dict
for word in str1:
    words_str1[ word ] = True
    
for word in str2:
    words_str2[ word ] = True
    
    
# Result list
res = {}

for word in str1:
    if( not words_str2.get( word, None )):
        res[ word ] = True
        
for word in str2:
    if( not words_str1.get( word, None ) ):
        res[ word ] =True
        
# Print result
for word in res:
    print( word )
```
