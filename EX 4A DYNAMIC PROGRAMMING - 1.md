# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To find longest common subsequence using Dynamic Programming.



## Algorithm
1.Initialize the DP table: Create a table dp[m+1][n+1] filled with zeros.

2.Fill the DP table: If characters match, set dp[i][j] = dp[i-1][j-1] + 1; otherwise, set dp[i][j] = max(dp[i-1][j], dp[i][j-1]).

3.Find the LCS length: The length is stored in dp[m][n].

4.Backtrack: Start from dp[m][n], add matching characters, and move according to the table values.

5.Return the LCS: Reverse the string and return it.   

## Program:
~~~
Program to implement the longest common subsequence using Dynamic Programming

.
Developed by: RAKSHITHA K 
Register Number: 212223110039 

def lcs(u, v):
    """Return c where c[i][j] contains length of LCS of u[i:] and v[j:]."""
    c = [[-1]*(len(v) + 1) for _ in range(len(u) + 1)]
    for i in range(len(u) + 1):
        c[i][len(v)] = 0
    for j in range(len(v)):
        c[len(u)][j] = 0
 
    for i in range(len(u) - 1, -1, -1):
        for j in range(len(v) - 1, -1, -1):
            if u[i] == v[j]:
                c[i][j] = 1 + c[i + 1][j + 1]
            else:
                c[i][j] = max(c[i + 1][j], c[i][j + 1])
    return c
 
def print_lcs(u, v, c):
    """Print one LCS of u and v using table c."""
    i = j = 0
    while not (i == len(u) or j == len(v)):
        if u[i] == v[j]:
            print(u[i], end='')
            i += 1
            j += 1
        elif c[i][j + 1] > c[i + 1][j]:
            j += 1
        else:
            i += 1
 
u = input()
v = input()
c = lcs(u, v)
print_lcs(u, v, c)
~~~

## Output:
![image](https://github.com/user-attachments/assets/2e38966c-869f-44ca-9a0c-ded7e249391a)

## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
