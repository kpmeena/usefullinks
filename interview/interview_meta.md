https://leetcode.com/discuss/explore/facebook/1197242/Facebook-online-screening-questions

remove items with val ==0 from the linked list, similar to
https://leetcode.com/problems/remove-linked-list-elements/

https://leetcode.com/problems/remove-element/

Given boolean array of days at work, [T, F, T, T, F, F, F, T] and pto (number of PTOs one can take) - where boolean T means paid holiday and F means you can take a PTO. Find the maximum length of vacation an employee can take.
int findMaxVacationLength(year = [F, T, F, T, F, T, F, ], pto = 2) should return 5 because if we take PTO on indices year[2] and year[4], then we can get the maximum length vacation (consecutive T's).
similar to : https://leetcode.com/problems/max-consecutive-ones-iii/

-----

https://leetcode.com/discuss/interview-question/516166/facebook-onsite-reddit-upvote-system

The focus here is on the data structures and solution, not system design. Let me know if you need more clarification.

The problem is to implement two reddit features, being able to upvote/downvote a post and being able to get x top posts. For the "post" structure it can be as simple as an id and number of votes.

something like this:

class Post  {
	int id;
	int upvotes;
}

class Reddit {
	public void upvoteDownvote(int postID) {
	}
 
	public List<Integer> getTopKPosts(int k) {
	}
}
Im not sure how to solve this problem, first thing that comes to mind is to use a heap to keep track of most upvoted posts but if you upvote/downvote that post you need to update the heap and somehow find that one post, you could make a helper map or something to keep track of that instance of the post class with an id. The second thing that comes to mind is perhaps a linked list that we manually sort, after the inital setup of application, since a upvote/downvote is only adding or subtracting 1 to the value we can compare the node to its neighbors and move it accordingly.

Clarification question for interviewer : How to break tie ? Means what if two posts has same votes and which one to pick in top k.

Other than that, this is same as https://leetcode.com/problems/design-a-leaderboard/

AddScore API can be converted into upvote (+1) and downvote(-1).
----

https://leetcode.com/discuss/interview-question/3747462/Meta-Tech-Screen

Clone Graph where the graph could be unconnected. The input is a Graph object with a list of Node objects. Node objects represent the vertices in the graph

class Graph {
List vertices;
}

class Node {
String name = "";
List neighbors;
}

public Graph cloneGraph(Graph input) {
// Create a deep copy of the graph and return the copy
}

