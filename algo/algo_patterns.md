
https://cses.fi/book/book.pdf

-----------
line segments

1. https://courses.engr.illinois.edu/cs374/sp2020/B/hw/hw_05_extra.pdf
facebook - bruteforce and optimal
Suppose we are given two sets of n points, one set {p1, p2, . . . , pn} on the line y = 0 and the other
set {q1, q2, . . . , qn} on the line y = 1. Consider the n line segments connecting each point pi to the
corresponding point qi
. Describe and analyze a divide-and-conquer algorithm to determine how
many pairs of these line segments intersect, in O(n log n) time. See the example below.


----
Branch cutting -- buckets and subsets and subsetsum - pruning and optimization

1. https://leetcode.com/problems/find-minimum-time-to-finish-all-jobs/discuss/1009817/one-branch-cutting-trick-to-solve-three-leetcode-questions
2. https://leetcode.com/problems/find-minimum-time-to-finish-all-jobs/

Two other similar questions are

1. https://leetcode.com/problems/matchsticks-to-square/
2. https://leetcode.com/problems/partition-to-k-equal-sum-subsets/
----
ADJACENT houses/elements in array

1. https://leetcode.com/problems/delete-and-earn/
2. https://leetcode.com/problems/house-robber/
3. https://leetcode.com/problems/house-robber-ii/
4. https://leetcode.com/problems/paint-house/

https://leetcode.com/discuss/interview-question/3782629/Chubb-OA

-----

jump game score
1. https://leetcode.com/problems/jump-game-vi/    -- jump at most k steps forward. Return the maximum score. DEQUE is optimal

can we also use FOR loop here since we have (n-i) choices here i am getting confused when to use for loop and when not

2. https://leetcode.com/problems/visit-array-positions-to-maximize-score/   - can jump to any pos in right. reduce score when parity is diff. 2D dp. 

jump game - min steps

3. https://leetcode.com/problems/jump-game-iv/   -- jump to i+1, i-1 or arr[i] == arr[j]. return minimum number of steps 

-----
Binary search
https://labuladong.gitbook.io/algo-en/iii.-algorithmic-thinking/detailedbinarysearch

-----
1. set, unset ith bit, check if ith bit is set -
   https://www.hackerearth.com/practice/algorithms/dynamic-programming/bit-masking/tutorial/

3. https://leetcode.com/problems/special-permutations/  -- bitmask dp, permutations, backtracking? bruteforce

4. https://leetcode.com/problems/task-scheduler/   - grouping and freq

5. https://leetcode.com/problems/single-number-iii/

8. https://leetcode.com/problems/maximize-distance-to-closest-person/  --  seat a person with max distance with neighbor

9. https://leetcode.com/problems/exam-room/  -- Seat a person with max distance with neighbor

12. https://leetcode.com/problems/cheapest-flights-within-k-stops/ -- bellman ford

13. https://leetcode.com/problems/network-delay-time/ -- djikstra

14. https://leetcode.com/problems/find-eventual-safe-states/   - directed graph cycles - using 3 colors

---
Contribution 

1. https://leetcode.com/problems/sum-of-subarray-ranges/   -- contribution
2. https://leetcode.com/problems/sum-of-subarray-minimums/
3. https://leetcode.com/problems/largest-rectangle-in-histogram/

-----
knapsack

1. https://leetcode.com/problems/delete-and-earn/  -- knapsack, recurrence relation
2. https://leetcode.com/problems/maximum-value-of-k-coins-from-piles/  -- knapsack
3. 

---
3-sum

1. https://leetcode.com/problems/valid-triangle-number/  -- 3 sum, start from right
So 3 side lengths a, b, c can form a Triangle if and only if a + b > c && a + c > b && b + c > a.

2. https://leetcode.com/problems/3sum-smaller/  --  k-j pattern, 3 sum, 2 sum
    if 1+2 ..4,6, +7 is < target, then 1+2 +6, 1+2+4 all will form a result. 1+2 is constant, dicard 2 (j) j++

----

Weighted interval scheduling/unweighted interval scheduling
1. https://leetcode.com/problems/maximum-number-of-events-that-can-be-attended/  -- unweighted
2. https://leetcode.com/problems/maximum-number-of-events-that-can-be-attended-ii/  -- weighted (like 
3. https://leetcode.com/problems/maximum-profit-in-job-scheduling/
---
construct binary tree
https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/
https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/

---

Random

1. Given an integer n and a list of integers l, write a function that randomly generates a number from 0 to n-1 that isn't in l (uniform).
2. https://leetcode.com/problems/implement-rand10-using-rand7/


