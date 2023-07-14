https://en.wikipedia.org/wiki/Shunting_yard_algorithm - fiddly, lot of code for some cases
calculator problems - infix to postfix (reverse polish notation) - uses stack and queue

---
distance -> manhattan, eulicd
https://www.cuemath.com/euclidean-distance-formula/ a^2 = b^2 + c^2

b = distance in x -> x2-x1, c = distance in y -> y2-y1 a = sqrt ( (x2-x1) ^ 2 + (y2-y1) ^ 2 )

manhattan distance walk the grid - x2-x1 + y2-y1
---

**colinear ** https://www.cuemath.com/geometry/collinearity/ As per the Euclidean geometry, a set of points are considered to be collinear, if they all lie in the same line, How To Determine if the Points Are Collinear? There are various methods to find out whether three points are collinear or not. These methods are given as follows:

Using Distance Formula Slope Method ****** For 3 points -> P, Q, R, slope of (P,Q) == slope of (P, R) Area of Triangle Method)

---

calculator problems -> left, right associativity. PEMDAS, Unary -> 1-(-2)


For operators, associativity means that when the same operator appears in a row, then which operator occurence we apply first. In the following, let Q be the operator

a Q b Q c
If Q is left associative, then it evaluates as

(a Q b) Q c
And if it is right associative, then it evaluates as

a Q (b Q c)
It's important, since it changes the meaning of an expression. Consider the division operator with integer arithmetic, which is left associative

4 / 2 / 3    <=>    (4 / 2) / 3    <=> 2 / 3     = 0
If it were right associative, it would evaluate to an undefined expression, since you would divide by zero

4 / 2 / 3    <=>    4 / (2 / 3)    <=> 4 / 0     = undefined
