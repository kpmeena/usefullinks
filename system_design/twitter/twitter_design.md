https://www.youtube.com/watch?v=z8LU0Cj6BOU&ab_channel=USENIX LISA '10 - Operations at Twitter: Scaling Beyond 100 Million Users

https://www.infoq.com/presentations/Twitter-Timeline-Scalability/ Raffi

https://github.com/donnemartin/system-design-primer/blob/master/solutions/system_design/twitter/README.md donne martin

text of raffi's presentation
http://highscalability.com/blog/2013/7/8/the-architecture-twitter-uses-to-deal-with-150m-active-users.html
--------
Functional requirements

Users should be able to post tweets
Home timeline - Users should be able to view tweets of people who they follow
Users should be able to search tweets
---
Scope

How many DAU (Daily Active Users)? 500 million
Traffic?
RPS - requests per second?
tweets per second?

---
Capacity Estimation - Back of the envelope

tweet size = 140 chars? 280 bytes? A char represents a character in Java (*). It is 2 bytes large (or 16 bits).

tweet media size ? - 10 KB?

tweets per second on average? 500 million tweets per day

10 KB per tweet * 500 million tweets per day = 500 million * 10 KB = 5000 million = 5 billion KB = 5 TB. 150 TB per month

Kilo, Mega, Giga, Tera, Peta bytes - Ki M Gi Te Pe
---

Data Model

User table -> user details, user_id, name, email etc

Followings table. user -> followings (1 - Many). john follows 100 people user_id following_id

Followers table? John's followers

tweets table

so, many to many means 1-n from both the sides.

one-to-many relationship: One customer can order many items.

The many-to-many relationship is better described by a book sample:

An author can write many books (that would be a one-to-many relationship). But he can have co-authors also involved - one book can have many authors.
----

Services

Home Timeline service - user views tweets from the people they follow User Time Service - user views their own tweets

HLD

---
http://highscalability.com/blog/2013/7/8/the-architecture-twitter-uses-to-deal-with-150m-active-users.html

High Level For Pull Based Timelines

Tweet comes in over a write API. It goes through load balancers and a TFE (Twitter Front End) and other stuff that won’t be addressed.
This is a very directed path. Completely precomputed home timeline. All the business rules get executed as tweets come in.
Immediately the fanout process occurs. Tweets that come in are placed into a massive Redis cluster. Each tweet is replicated 3 times on 3 different machines. At Twitter scale many machines fail a day.

Fanout queries the social graph service that is based on Flock. Flock maintains the follower and followings lists.
Flock returns the social graph for a recipient and starts iterating through all the timelines stored in the Redis cluster.
The Redis cluster has a couple of terabytes of RAM.

Pipelined 4k destinations at a time
Native list structure are used inside Redis.

Let’s say you tweet and you have 20K followers. What the fanout daemon will do is look up the location of all 20K users inside the Redis cluster. Then it will start inserting the Tweet ID of the tweet into all those lists throughout the Redis cluster. So for every write of a tweet as many as 20K inserts are occurring across the Redis cluster.

What is being stored is the tweet ID of the generated tweet, the user ID of the originator of the tweet, and 4 bytes of bits used to mark if it’s a retweet or a reply or something else.

Your home timeline sits in a Redis cluster and is 800 entries long. If you page back long enough you’ll hit the limit. RAM is the limiting resource determining how long your current tweet set can be.

Every active user is stored in RAM to keep latencies down.

Active user is someone who has logged into Twitter within 30 days, which can change depending on cache capacity or Twitter’s usage.
If you are not an active user then the tweet does not go into the cache.

Only your home timelines hit disk.
If you fall out of the Redis cluster then you go through a process called reconstruction.

Query against the social graph service. Figure out who you follow. Hit disk for every single one of them and then shove them back into Redis.
It’s MySQL handling disk storage via Gizzard, which abstracts away SQL transactions and provides global replication.

By replicating 3 times if a machine has a problem then they won’t have to recreate the timelines for all the timelines on that machine per datacenter.
If a tweet is actually a retweet then a pointer is stored to the original tweet.
When you query for your home timeline the Timeline Service is queried. The Timeline Service then only has to find one machine that has your home timeline on it.
Effectively running 3 different hash rings because your timeline is in 3 different places.
They find the first one they can get to fastest and return it as fast as they can.
The tradeoff is fanout takes a little longer, but the read process is fast. About 2 seconds from a cold cache to the browser. For an API call it’s about 400 msec.
Since the timeline only contains tweet IDs they must “hydrate” those tweets, that is find the text of the tweets. Given an array of IDs they can do a multiget and get the tweets in parallel from T-bird.
Gizmoduck is the user service and Tweetypie is the tweet object service. Each service has their own caches. The user cache is a memcache cluster that has the entire user base in cache. Tweetypie has about the last month and half of tweets stored in its memcache cluster. These are exposed to internal customers.
Some read time filtering happens at the edge. For example, filtering out Nazi content in France, so there’s read time stripping of the content before it is sent out.
