July 2023

https://leetcode.com/discuss/interview-question/3784161/Amazon-or-OA-or-Get-Popularity-of-movie

Amazon organized a movie festival to promote its online video- streaming platform, amazon prime video.
In the festival, movies of 2 categories, "comedy" and "drama" were played on a loop. The original sequence of movies is represented as a binary string, where a comedy movie is denoted by '0', and a drama is '1'. The movies are on a continuous loop, so if the original sequence of movies is "01101" and is concatenated infinitely so they are played in the order "011010110101101. . . . ".
The popularity of the festival is the number of times the difference between the number of comedies and dramas played so far (that is the prefix till that index) is exactly equal to diff. More formally, the popularity of the festival is the number of prefixes in the concatenated string for which count('0') - count('1') = diff.

Given the original sequence of movies denoted by movieorder, and the popularity parameter diff, find the popularity of the festival. If there are infinite such instances possible, return "-1". If there is no such instance possible, return "0".

Notes:
• a binary string consists of characters '0'and '1
• empty strings are also considered.

Example
the sequence movieorder="110100" and diff=-1.
prefixes of lengths 3, 9, 15, 21, satisfy the constraint of diff--1.
Since there are an infinite number of instances that satisfy the requirement, the answer is-1.

Function description:
Complete the function getpopularity in the editor below.

getpopularity has the following parameters:
string movieorder: the original order of movies.
Int diff: the required value of count(0)-count(1)

Returns
int: the popularity of the festival, or 1
------

OA - july 10 2023

Find the number of subarrays in a given integer array whose maximum element is either equal to left or right element of subarray.
Test Case:
{3,1,3,5} - > 10 // All subarrays satisfy the condition
{2, 5, 3} -> 5 // {2,5,3} Subarray doesn't satisy condition
Looking for solution better O(n*n).

same as -

https://leetcode.com/discuss/interview-question/3719223/amazon-sde-oa-2023-find-maximum-profitable-months/1957207

A team of analysts at Amazon needs to analyze the stock prices of Amazon over a period of several months.

A group of consecutively chosen months is said to be maximum profitable
if the price in its first or last month is the maximum for the group.
More formally, a group of consecutive months [l, r] (1 ≤ l ≤ r ≤ n) is said to be maximum profitable if either:

stockPrice[l] = max(stockPrice[l], stockPrice[l + 1], ..., stockPrice[r]) 
stockPrice[r] = max(stockPrice[l], stockPrice[l + 1], ..., stockPrice[r])  
Given prices over n consecutive months, find the number of maximum profitable groups which can be formed.
Note that the months chosen must be consecutive, i.e., you must choose a subarray of the given array.

Example:
Consider there are n = 3 months of data, stockPrice = [2, 3, 2]
There will be 5 profitable months:
[[2], [2, 3], [3], [3, 2], [2]]


It's a monotonic stack question.

I think the tricky part is stockPrice[l] == stockPrice[r] and we cannot double count.
However, with a good understanding on the monotonic stack this is not a problem and doesn't need to be handled specially.



def solution(v: List[int]) -> int:
    stack = []
    n, r = len(v), 0
    for i in range(0, n):
        while len(stack) and v[stack[-1]] < v[i]:
            # [top..i - 1] is what we want. Note it may contain equal elements.
            r += i - stack.pop()
        r += i - (stack[-1] if len(stack) else -1)
        stack.append(i)
    while len(stack):
        # [top..n - 1] is what we want
        r += n - stack.pop()
    return r - n

print(solution([1, 1, 1, 1]))
print(solution([2, 3, 2]))
print(solution([5, 3, 1, 3, 5]))
