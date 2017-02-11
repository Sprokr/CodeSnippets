# Array - DS

An array is a type of data structure that stores elements of the same type in a contiguous block of memory. In an array, , of size , each memory location has some unique index,  (where ), that can be referenced as  (you may also see it written as ).

Given an array, , of  integers, print each element in reverse order as a single line of space-separated integers.

Note: If you've already solved our C++ domain's Arrays Introduction challenge, you may want to skip this.

**Input Format**

The first line contains an integer,  (the number of integers in ). 
The second line contains  space-separated integers describing .

**Constraints**

Output Format

Print all  integers in  in reverse order as a single line of space-separated integers.

**Sample Input**

4
1 4 3 2

**Sample Output**

2 3 4 1



##**C Code -**

```
#include <math.h>
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <assert.h>
#include <limits.h>
#include <stdbool.h>

int main(){
    int n; 
    scanf("%d",&n);
    int *arr = malloc(sizeof(int) * n);
    for(int arr_i = 0; arr_i < n; arr_i++){
       scanf("%d",&arr[arr_i]);
    }
    for(int arr_i = n-1; arr_i >=0; arr_i-- ){
        printf("%d ",arr[arr_i]);
    }
    return 0;
}
```

##Python Code -

```
#!/bin/python

import sys


n = int(raw_input().strip())
arr = map(int,raw_input().strip().split(' '))
for i in arr[::-1]:
    print(i),

```

