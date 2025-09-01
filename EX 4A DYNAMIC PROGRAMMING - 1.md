# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To Create a python program to find the length of longest common subsequence using naive recursive method.

## Algorithm
1. Initialize a matrix with zeros, representing LCS lengths for substrings.
2. Iterate through both strings, filling the matrix.
3. If characters match, add 1 to the diagonal element (from previous LCS).
4. If characters don't match, take the maximum from the cell above or to the left (previous LCS without one character).
5. Return the value in the bottom-right corner of the matrix, which holds the LCS length.

## Program:


```
def lcs(str1 , str2):
    m = len(str1)
    n = len(str2)
    matrix = [[0]*(n+1) for i in range(m+1)] 
    for i in range(m+1):
        for j in range(n+1):
            if i==0 or j==0:
                matrix[i][j] = 0
            elif str1[i-1] == str2[j-1]:
                matrix[i][j] = 1 + matrix[i-1][j-1]
            else:
                matrix[i][j] = max(matrix[i-1][j] , matrix[i][j-1])
    return matrix[-1][-1]
str1 = input()
str2 = input()
lcs_length = lcs(str1, str2)
print("Length of LCS is  {}".format(lcs_length))
```

## Output:

![image](https://github.com/user-attachments/assets/f82628d3-3d25-4890-8efe-12af2afeef17)

## Result:
Thus the program was executed successfully for computing  to find the length of longest common subsequence using naive recursive method.
