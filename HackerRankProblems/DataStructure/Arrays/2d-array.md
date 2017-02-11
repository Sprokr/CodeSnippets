# 2D - Array
####Context 
Given a  2D Array, :

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
```

We define an hourglass in  to be a subset of values with indices falling in this pattern in 's graphical representation:


```
a b c
  d
e f g
```
There are  hourglasses in , and an hourglass sum is the sum of an hourglass' values.

####Task
Calculate the hourglass sum for every hourglass in , then print the maximum hourglass sum.

**Note**: If you have already solved the Java domain's Java 2D Array challenge, you may wish to skip this challenge.

####Input Format

There are  lines of input, where each line contains  space-separated integers describing 2D Array ; every value in  will be in the inclusive range of  to .

**Constraints**

- -9 <= A[i][j] <= 9
- 0 <= i,j <= 5

**Output Format**

Print the largest (maximum) hourglass sum found in .

**Sample Input**

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 2 4 4 0
0 0 0 2 0 0
0 0 1 2 4 0
```
**Sample Output**

19

**Explanation**

A contains the following hourglasses:

```
1 1 1   1 1 0   1 0 0   0 0 0
  1       0       0       0
1 1 1   1 1 0   1 0 0   0 0 0

0 1 0   1 0 0   0 0 0   0 0 0
  1       1       0       0
0 0 2   0 2 4   2 4 4   4 4 0

1 1 1   1 1 0   1 0 0   0 0 0
  0       2       4       4
0 0 0   0 0 2   0 2 0   2 0 0

0 0 2   0 2 4   2 4 4   4 4 0
  0       0       2       0
0 0 1   0 1 2   1 2 4   2 4 0
```
The hourglass with the maximum sum () is:

```
2 4 4
  2
1 2 4
```

## C Code -

```

#include <math.h>
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <assert.h>
#include <limits.h>
#include <stdbool.h>

int main(){
    int arr[6][6];
    for(int arr_i = 0; arr_i < 6; arr_i++){
       for(int arr_j = 0; arr_j < 6; arr_j++){
          scanf("%d",&arr[arr_i][arr_j]);
       }
    }
    int maxSum = 0;
    int count = 0;
    for(int i = 0; i < 4; i++){
        for(int j =0; j< 4; j++){
            int currSum = arr[i][j]+arr[i][j+1]+arr[i][j+2]+arr[i+1][j+1]+arr[i+2][j]+arr[i+2][j+1]+arr[i+2][j+2];
            if(currSum > maxSum || count == 0){
                maxSum = currSum;
            }
            count++;
        }
    }
    printf("%d", maxSum);
    return 0;
}

```

## Python Code -

```
#!/bin/python

import sys


arr = []
for arr_i in xrange(6):
    arr_temp = map(int,raw_input().strip().split(' '))
    arr.append(arr_temp)

maxSum = 0
count = 0

for i in range(0,4):
    for j in range(0,4):
        currSum = arr[i][j]+arr[i][j+1]+arr[i][j+2]+arr[i+1][j+1]+arr[i+2][j]+arr[i+2][j+1]+arr[i+2][j+2]
        if(currSum > maxSum or count == 0):
            maxSum = currSum
        count+=1
print maxSum
```
