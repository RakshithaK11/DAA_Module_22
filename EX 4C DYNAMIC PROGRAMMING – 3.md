# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm
1.Initialize the DP table: Create a 2D table dp[n][n] where n is the length of the sequence, and initialize each dp[i][i] = 1 (single characters are palindromes of length 1).

2.Fill the DP table: For each pair of indices (i, j), if sequence[i] == sequence[j], set dp[i][j] = dp[i+1][j-1] + 2; otherwise, set dp[i][j] = max(dp[i+1][j], dp[i][j-1]).

3.Iterate over subsequences: Loop through subsequences of increasing lengths to fill the DP table.

4.Track the longest length: The value at dp[0][n-1] holds the length of the longest palindromic subsequence.

5.Return the length: Return the value stored in dp[0][n-1], which is the length of the longest palindromic subsequence.

## Program:
~~~
Program to implement to find the length of the longest palindromic subsequence in it

Developed by: RAKSHITHA K
Register Number: 212223110039

dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n))
~~~

## Output:
![image](https://github.com/user-attachments/assets/842567b0-2589-487c-b57b-fac462b8551f)

## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
