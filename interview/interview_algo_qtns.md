july 9 2023 - Uber

You are trying to detect if two given documents are similar. 
You need to build a function that when given two sentences as strings indicates whether the two sentences are similar. 
You’re given an array of string pairs where each pair of words indicate that the two words are similar.

Your function should return true if sentence1 and sentence2 are similar, or false if they are not similar.
Two sentences are similar if:

They have the same length (i.e., the same number of words)
Corresponding words are similar.
Notice that a word is always similar to itself, also notice that the similarity relation is transitive. For example, if the words a and b are similar, and the words b and c are similar, then a and c are similar.
https://leetcode.com/discuss/interview-question/3740143/Uber-or-SSE-or-DSA

---------


-------
https://leetcode.com/discuss/interview-question/3742634/Amazon-or-OA

Find the number of subarrays in a given integer array whose maximum element is either equal to left or right element of subarray.
Test Case:
{3,1,3,5} - > 10 // All subarrays satisfy the condition
{2, 5, 3} -> 5 // {2,5,3} Subarray doesn't satisy condition
Looking for solution better O(n*n).

--
https://leetcode.com/discuss/interview-question/3739478/Atlassian-or-OA-or-return-number-of-neighboring-houses

Atlassian

There are houses on a straight line. We are given instructions to delete some houses. It is guaranteed that the instructions will be given for valid houses. Return a list of the number of neighboring houses after each instruction.

Example: houses = [2, 1, 3, 4, 6, 7, 9], instructions = [6, 3, 9]. The result should be [3, 4, 3].
Sort the houses: [1, 2, 3, 4, 6, 7, 9]
After step 1, the houses are [1, 2, 3, 4, 7, 9]; the neighboring house groups are (1, 2, 3, 4), (7), (9)
After step 1, the houses are [1, 2, 4, 7, 9]; the neighboring house groups are (1, 2), (4), (7), (9)
After step 1, the houses are [1, 2, 4, 7]; the neighboring house groups are (1, 2), (4), (7)

--------

https://leetcode.com/discuss/interview-question/3781043/hackerrank-oa

Q1

	There is an array A of N non-negative integers. Any two initial elements of A that are adjacent can be replaced with their merged equivalent. For example, given A = [2, 3, 15], pair (2, 3) can be replaced with 23, resulting in array [23, 15], and pair (3, 15) can be replaced with 315, resulting in array [2, 315]. The result of the merge cannot be merged any further, so we can't get 2315 in the example above. What is the maximum possible sum of elements of A!! after any number of merges?
Write a function:
def solution(A)
that, given an array A of N non-negative integers, returns the maximum sum of elements of A after any number of merges.
Examples:
1. Given A = [2, 2, 3, 5, 4, 0] the function should return 97. We can merge elements of the following pairs: (2, 2), (3, 5) and (4, 0). This results in A = [22, 35, 40], which sums up to 97.
2. Given A = [3, 19, 191, 91, 3] the function should return 20107. We can merge elements of the following pairs: (19, 191) and (91, 3). This results in A = [3, 19191, 913], which sums up to 20107.
3. Given A = [12, 6, 18, 10, 1, 0], the function should return 1946. The merges should make A = [126, 1810, 10], which sums up to 1946.
4. Given A = [2, 1, 0, 1, 2, 9, 1, 0], the function should return 124. The merges should make A = [21, 0, 12, 91, 0], which sums up to 124. Write an efficient algorithm for the following assumptions:
• N is an integer within the range [1..10,000];
each element of array A is an integer within the range [0..200].
Q2


AND is a standard bitwise operation. For example, given K = 12 (binary representation 01100) and L = 21 (binary representation 10101) we obtain: 01100 AND 10101 =
00100
The AND operation can be extended to N integers, for example:
01100 AND
10101 AND
00100 =
00100
Because AND of 01100 (first argument) and 10101 (second argument) is 00100, and AND of this number with 00100 (third argument) is also 00100. Write a function:
def solution(A)
that, given an array A consisting of N integers, returns the size of the largest possible subset of A such that AND of all its elements is greater than 0. Examples:
1. Given A = [13, 7, 2, 8, 3] your function should return 3.
We can pick subset 13, 7 and 3. AND of these elements is positive and it is the largest possible subset of numbers that fulfills the criteria.
1101 (13) AND
0111 (7) AND
Examples: 1. Given A = [13, 7, 2, 8, 3] your function should return 3.
We can pick subset 13, 7 and 3. AND of these elements is positive and it is the largest possible subset of numbers that fulfills the criteria.
1101 (13) AND
0111 (7) AND
0011 (3) =
0001 (1)
2. Given A = [1, 2, 4, 8] your function should return 1. The AND of each pair from the array is equal to 0.
3. Given A = [16, 16] your function should return 2. The AND of both numbers is 16.
Write an efficient algorithm for the following assumptions:
⚫ N is an integer within the range [1..100,000];
⚫ each element of array A is an integer within the range [1..1,000,000,000].
Remember, all submissions are being checked for plagiarism.

----
July 20
https://leetcode.com/discuss/interview-question/3791790/Adobe-OA

The country has N cities and M bidirectional bridges of types 1,2 and 3. Some citizens of the country are affected by fruit and are called smilers.

a. Bridges of type 3 can be used by everyone

b. Bridges of type 2 can be used only by smilers

C. Bridges of type 1 can only be used by non-smilers

Omesh has an interesting query for you, how many bridges can you destroy such that the country is still connected? A connected country is a country where all citizens can go from one city to another..

Input format:

The first line contains integers N and M.
The following M lines contain the edges described by three integers A, B, and C .
A and B are the two cities numbered between 1 and N and C is the type of road.

Output:

Single integer denoting the number of roads that can be already disconnected, print-1 if Wano is already disconnected.

Constraints

T < 10

N, M< 10^4

1 <= A, B<= N

Sample Input
5 7
1 2 3
2 3 3
3 4 3
5 3 2
5 4 1
5 2 2
1 5 1
Sample Output
2

Memory Limit: 400 (in MB) Time Limit: 5 (in Seconds)
https://leetcode.com/problems/remove-max-number-of-edges-to-keep-graph-fully-traversable/
