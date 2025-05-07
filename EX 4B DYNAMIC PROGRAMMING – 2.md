# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm
1.Initialize the DP table: Create a 2D table dp[m+1][n+1] and set all values to 0.

2.Fill the DP table: If characters match, set dp[i][j] = dp[i-1][j-1] + 1; otherwise, set dp[i][j] = 0.

3.Track the maximum length: Keep track of the maximum value in the table, which indicates the length of the longest common substring.

4.Backtrack to find the substring(s): Start from the maximum value and backtrack to extract the longest common substring.

5.Return the substring(s): Return the substring(s) corresponding to the maximum length.

## Program:
~~~
Program to implement the longest common substring problem

Developed by: RAKSHITHA K
Register Number:  212223110039

def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
~~~

## Output:
![image](https://github.com/user-attachments/assets/0ebbfbb4-3823-43f0-8118-00dffb23d9d7)

## Result:
Thus the program was executed successfully for finding the longest common substring .
