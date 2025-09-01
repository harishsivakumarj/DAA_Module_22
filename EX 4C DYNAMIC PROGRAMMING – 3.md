# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
To Create a python program to find the longest palindromic substring using Brute force method in a given string.

## Algorithm
1. Initialize an empty string to store the longest palindrome found so far.
2. Iterate through each character of the input string, considering it as a potential center of a palindrome.
3. Expand outwards from each character to find the longest odd-length palindrome centered there.
4. Expand outwards from between each pair of characters to find the longest even-length palindrome centered there.
5. Update the longest palindrome found if a longer one is discovered.  

## Program:


```
def expand(s, low, high):
    length = len(s)
    while low >= 0 and high < length and s[low] == s[high]:
        low = low - 1
        high = high + 1
    return s[low + 1:high]
 
def findLongestPalindromicSubstring(s):
    if not s or not len(s):
        return ''
    max_str = ''
    max_length = 0
 
    for i in range(len(s)):
        curr_str = expand(s, i, i)
        curr_length = len(curr_str)
 
        if curr_length > max_length:
            max_length = curr_length
            max_str = curr_str
 
        curr_str = expand(s, i, i + 1)
        curr_length = len(curr_str)
 
        if curr_length > max_length:
            max_length = curr_length
            max_str = curr_str
    return max_str
 
if __name__ == '__main__':
    s = input()       
    print(findLongestPalindromicSubstring(s))
```
## Output:

![image](https://github.com/user-attachments/assets/f824cda1-0d98-4356-9f62-1665a8f9a656)

## Result:
Thus the program was executed successfully to find the longest palindromic substring using Brute force method in a given string.
