https://www.youtube.com/watch?v=z8LU0Cj6BOU&ab_channel=USENIX LISA '10 - Operations at Twitter: Scaling Beyond 100 Million Users

https://www.infoq.com/presentations/Twitter-Timeline-Scalability/ Raffi

https://github.com/donnemartin/system-design-primer/blob/master/solutions/system_design/twitter/README.md donne martin

--------
Functional requirements

Users should be able to post tweets
Users should be able to read tweets of people who they follow
Users should be able to search tweets
----------------
Scope

How many DAU (Daily Active Users)?
Traffic?
RPS - requests per second?
tweets per second?

-------------
Capacity Estimation - Back of the envelope

tweet size = 140 chars? 280 bytes? A char represents a character in Java (*). It is 2 bytes large (or 16 bits).

tweet media size ? - 10 KB?

tweets per second on average? 500 million tweets per day

10 KB per tweet * 500 million tweets per day = 500 million * 10 KB = 5000 million = 5 billion KB = 5 TB. 150 TB per month

Kilo, Mega, Giga, Tera, Peta bytes
------------------------

Data Model

User table -> user details, user_id, name, email etc

Followings table. user -> followings (1 - Many). john follows 100 people user_id following_id

Followers table? John's followers

tweets table

so, many to many means 1-n from both the sides.

one-to-many relationship: One customer can order many items.

The many-to-many relationship is better described by a book sample:

An author can write many books (that would be a one-to-many relationship). But he can have co-authors also involved - one book can have many authors.
-----

Services

Home Timeline service - user views tweets from the people they follow User Time Service - user views their own tweets

HLD
