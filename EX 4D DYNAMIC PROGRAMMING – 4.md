# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To Create a Naive recursive python program to find the minimum number of operations to convert str1 to str2.

## Algorithm
1. Handle base cases: If one string is empty, the distance is the length of the other.
2. Compare last characters: If they match, the cost is 0; otherwise, the cost is 1.
3. Recursively calculate the cost of three operations: insertion, deletion, and substitution.
4. Return the minimum of these three operation costs.
5. Repeat until both strings are empty, summing costs along the chosen path. 

## Program:


```
def LD(s, t):
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1,
               LD(s, t[:-1])+1, 
               LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))
```
## Output:

![image](https://github.com/user-attachments/assets/2db44139-019c-4291-8f37-04299f05c8cd)

## Result:
Thus the program was executed successfully to find the minimum number of operations to convert str1 to str2.

