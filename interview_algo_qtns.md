july 9 2023 - Uber

You are trying to detect if two given documents are similar. You need to build a function that when given two sentences as strings indicates whether the two sentences are similar. You’re given an array of string pairs where each pair of words indicate that the two words are similar.

Your function should return true if sentence1 and sentence2 are similar, or false if they are not similar.
Two sentences are similar if:

They have the same length (i.e., the same number of words)
Corresponding words are similar.
Notice that a word is always similar to itself, also notice that the similarity relation is transitive. For example, if the words a and b are similar, and the words b and c are similar, then a and c are similar.
https://leetcode.com/discuss/interview-question/3740143/Uber-or-SSE-or-DSA

---------
https://leetcode.com/discuss/interview-question/350248/Google-or-Summer-Intern-OA-2019-or-Stores-and-Houses
Google

You are given 2 arrays representing integer locations of stores and houses (each location in this problem is one-dementional). For each house, find the store closest to it.
Return an integer array result where result[i] should denote the location of the store closest to the i-th house. If many stores are equidistant from a particular house, choose the store with the smallest numerical location. Note that there may be multiple stores and houses at the same location.

Example 1:

Input: houses = [5, 10, 17], stores = [1, 5, 20, 11, 16]
Output: [5, 11, 16]
Explanation: 
The closest store to the house at location 5 is the store at the same location.
The closest store to the house at location 10 is the store at the location 11.
The closest store to the house at location 17 is the store at the location 16.
Example 2:

Input: houses = [2, 4, 2], stores = [5, 1, 2, 3]
Output: [2, 3, 2]
Example 3:

Input: houses = [4, 8, 1, 1], stores = [5, 3, 1, 2, 6]
Output: [3, 6, 1, 1]

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
