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
