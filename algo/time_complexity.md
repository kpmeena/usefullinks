
 
 https://leetcode.com/problems/find-minimum-time-to-finish-all-jobs/

 exponential 
1st level -> k branches
2nd level -> k * k        (k ^ 2)
3rd level -> k * k * k    (k ^ 3) 

    I still don't get how its O(kn!). This is how I read it. Please correct me.
Ignoring all the pruning (I think pruning don't change the complexity).

on first level, we will have k branches with pos=n-1. 
on second, it will be k*k with pos=n-2, ..... k^n with pos=0. Since the depth will be n (size of jobs).
So the T should be O(k^n) or O(12^n) right?

-------

