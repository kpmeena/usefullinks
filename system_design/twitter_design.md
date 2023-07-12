https://www.youtube.com/watch?v=z8LU0Cj6BOU&ab_channel=USENIX
 LISA '10 - Operations at Twitter: Scaling Beyond 100 Million Users 

 https://www.infoq.com/presentations/Twitter-Timeline-Scalability/
 Raffi

 https://github.com/donnemartin/system-design-primer/blob/master/solutions/system_design/twitter/README.md
donne martin

-----

Functional requirements

1. Users should be able to post tweets
2. Users should be able to read tweets of people who they follow
3. Users should be able to search tweets

-------

Scope

1. How many DAU (Daily Active Users)?
2. Traffic?
3. RPS - requests per second?
4. tweets per second?
-----
Capacity Estimation - Back of the envelope

1. tweet size = 140 chars? 280 bytes? 
 A char represents a character in Java (*). It is 2 bytes large (or 16 bits).

2. tweet media size ? - 10 KB?
   
2. tweets per second on average?
   500 million tweets per day
   
    10 KB per tweet * 500 million tweets per day  = 500 million * 10 KB = 5000 million = 5 billion KB = 5 TB
    150 TB 

   Kilo, Mega, Giga, Tera, Peta bytes

------

Data Model

1. User table -> user details, user_id, name, email etc

2. Followings table. user -> followings (1 - Many). john follows 100 people
user_id  following_id

3. Followers table? John's followers

4. tweets table

so, many to many means 1-n from both the sides.

one-to-many relationship: One customer can order many items.

The many-to-many relationship is better described by a book sample:

An author can write many books (that would be a one-to-many relationship). 
But he can have co-authors also involved - one book can have many authors.

-------

