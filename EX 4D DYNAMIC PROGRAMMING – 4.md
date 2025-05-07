# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm
1.Base case 1: If str1 is empty, return the length of str2 (all insertions).

2.Base case 2: If str2 is empty, return the length of str1 (all deletions).

3.If characters match: If str1[i] == str2[j], no operation is needed, so call the function recursively with str1[i+1] and str2[j+1].

4.If characters don't match: Consider all three possible operations (insert, delete, or replace) and recursively find the minimum number of operations.

5.Return the minimum operations: Return the minimum value obtained from the insert, delete, and replace operations.

## Program:
~~~

Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

Developed by: RAKSHITHA K
Register Number:  212223110039

def LD(s, t):
    #########  Add your code here ###########
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1, LD(s, t[:-1])+1, LD(s[:-1], t[:-1]) + cost])
    return res
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))
~~~



## Output:
![image](https://github.com/user-attachments/assets/5493659f-e1bd-4422-b666-dadd2d05a2f9)

## Result:
Thus the program was executed successfully for finding edit distance between two strings.
