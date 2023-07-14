July 14 
https://leetcode.com/discuss/interview-question/3760132/Google-SWE-Intern-OA-2023-(India)

OA) Special Subsequence
A subsequence of a string is a new string that is formed by deleting some (or none) of the characters from the original string, without changing the order of the remaining characters.

A special subsequence of a string is a subsequence that has the following properties:

• It has a length of exactly K.

• It contains all unique characters.

• The sum of the frequencies of all the characters in the subsequence is the maximum possible sum among all special subsequences of length K.
Given a string S and an integer K, find the number of distinct special subsequences of the string. Since the number of special subsequences can be large, print the answer modulo 10^9 +7.

Constraints:
1 <= LEN(S) <= 10^5
1 <= K <= LEN(S)

1)Sample Input:
K = 4
S: "cppbg"
Output: 2

2)Sample Input:
K = 8
S: "fpbavjsmppdt"
Output: 108

3)Sample Input:
K = 7
S: "ppzfsncqyzmuwrcv"
OutputL 1680

QB) Finding Arrays
Given an array S of N element. We need to find the count of distinct arrays A of N elements that exists such that:

•A[i] < A[i+1] for all 1<= i< N
•Sum of digits of A[i] is equal to S[i] for all 1<=i<=N
•1<=A[i]<=1000
An array A is said to be different from array B if there exists an index i such that A[i] != B[i]

Since the count can be very large. Output the answer modulo 10^9 + 7

Note: Consider 1-based indexing

Constrains:
1 <= N <= 100
1 <= S[i] <= 30

1)Sample Input:
N = 2
S: 2 1
Output: 10

2)Sample Input:
N = 3
S: 10 15 16
Output: 101776

3)Sample Input:
N = 6
S: 3 6 10 14 12 17
Output: 142727553

4)Sample Input:
N = 9
S: 2 7 3 5 9 13 9 14 11
Output: 19829619
