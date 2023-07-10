OA - july 10 2023

Find the number of subarrays in a given integer array whose maximum element is either equal to left or right element of subarray.
Test Case:
{3,1,3,5} - > 10 // All subarrays satisfy the condition
{2, 5, 3} -> 5 // {2,5,3} Subarray doesn't satisy condition
Looking for solution better O(n*n).

same as -
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
