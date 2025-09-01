# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the two strings ‘X’ and ‘Y’, find the length of the longest common substring. 

## Algorithm
1. Initialize a matrix with zeros and a result variable to track the maximum length.
2. Iterate through both strings, filling the matrix based on character matches.
3. If characters match, increment the diagonal element and update result if it's a new maximum.
4. If characters don't match, reset the current cell to 0, breaking the current substring.
5. Return the result, which is the length of the longest common substring.
## Program:


```
def LCSubStr(X, Y, m, n):
    LCSuff = [[0 for k in range(n+1)] for l in range(m+1)]
    result = 0
 
    for i in range(m + 1):
        for j in range(n + 1):
            if (i == 0 or j == 0):
                LCSuff[i][j] = 0
            elif (X[i-1] == Y[j-1]):
                LCSuff[i][j] = LCSuff[i-1][j-1] + 1
                result = max(result, LCSuff[i][j])
            else:
                LCSuff[i][j] = 0
    return result
 
X = input()
Y = input()
m = len(X)
n = len(Y)
 
print('Length of Longest Common Substring is',
      LCSubStr(X, Y, m, n))
 
```
## Output:

![image](https://github.com/user-attachments/assets/8b127337-e25c-464a-ac2f-8d320a31f33c)

## Result:
Thus the program was executed successfully for finding the longest common substring .
