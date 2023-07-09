july 9 2023
You are trying to detect if two given documents are similar. You need to build a function that when given two sentences as strings indicates whether the two sentences are similar. You’re given an array of string pairs where each pair of words indicate that the two words are similar.

Your function should return true if sentence1 and sentence2 are similar, or false if they are not similar.
Two sentences are similar if:

They have the same length (i.e., the same number of words)
Corresponding words are similar.
Notice that a word is always similar to itself, also notice that the similarity relation is transitive. For example, if the words a and b are similar, and the words b and c are similar, then a and c are similar.
https://leetcode.com/discuss/interview-question/3740143/Uber-or-SSE-or-DSA

---------
https://leetcode.com/discuss/interview-question/3742634/Amazon-or-OA

Find the number of subarrays in a given integer array whose maximum element is either equal to left or right element of subarray.
Test Case:
{3,1,3,5} - > 10 // All subarrays satisfy the condition
{2, 5, 3} -> 5 // {2,5,3} Subarray doesn't satisy condition
Looking for solution better O(n*n).

