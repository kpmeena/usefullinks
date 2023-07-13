2023
https://leetcode.com/discuss/interview-experience/2008790/uber-phone-screen

You're given a set of symbols for the elements in the periodic table [.... Li, Be, B, C, N, F, Ne, Na, Co, Ni, Cu, Ga, Al, Si.....]

Write the function breakingBad(name, symbols) that given a name and a set of symbols returns the phrase with the following format [Symbol]rest of the word

Example:
symbols = [H, He, Li, Be, B, C, N, F, Ne, Na, Co, Ni, Cu, Ga, Al, Si, Fa]
breakingBad("henry alba", symbols) results in [He]nry [Al]ba

Follow up: we only care about the longest symbol within a word. Example in the word henry there are two elements that are present [H] & [He] and we want He in the output phrase and not H.

I am wondering how you would approach this problem?

My attempt to solving this during the interview was:

Put the symbols in a set for constant lookup time.
Find the maxLen of any symbol.
Break up the given string into multiple words (the only delimiter will be a blank space)
For each word look for the maxLen substring and then recurse on that substring with maxLen - 1 till maxLen == 0; and do that for each substring that can be formed.

------

https://leetcode.com/discuss/interview-question/1616210/google-india-new-grad-onsite-verify-the-rules

You are given various statements regarding some points and the direction between them. Check if all the statements are correct or not.

For example:

P1 is in North of P2
P2 is in North of P3
P3 is in North of P1

Output: False (since P3 will be in South of P1)

Daily coding problem-
Directions can be N,S,W,E,NW,NE,SW, etc.
The interviewer gave the hint to use graph.

A rule looks like this:

A NE B

This means this means point A is located northeast of point B.

A SW C

means that point A is southwest of C.

Given a list of rules, check if the sum of the rules validate. For example:

A N B
B NE C
C N A
does not validate, since A cannot be both north and south of C.

A NW B
A N B
is considered valid.
---

july 11
https://leetcode.com/discuss/interview-question/3740136/Uber-or-SSE-or-Screening-round

Parking in Uber inspection centres: Uber has vehicle inspection centres to inspect the quality of all new vehicles signing up to join the platform. As a Inspector in one of these Inspection centres you’re now charged to manage the vehicles coming in and leaving the inspection centre. Being a smart engineer you are, you’ve figured that you prefer to keep as much distance as possible between two vehicles to ease the inspection and avoid nuisance. You can assume that the parking lot is a straight line of individual parking spaces each numbered from 1 to N. As each vehicle comes in you want to assign it a parking spot.

Let’s say you assigned parking space 1 to the very first car now to maximise the distance you’d assign the next car to space N.
The next car now could be in the space N/2. (Whenever there are two positions each maximising the distance we will prefer the one with smaller index.).
Your problem now is to figure out the position at which the next incoming car should park. You can assume that the parking lot was empty when you started.
Vehicles leave the parking lot once their inspection is complete.
Implement the following functions: int insert_car() and remove_car(int pos)

https://leetcode.com/problems/exam-room/
-------
