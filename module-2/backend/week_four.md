## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?  
A delicious snack. Also data saved on the client device which allows some state to persist between http requests  
* What’s the difference between a session and a cookie?  
A session contains encrypted data, while a cookie is readable by humans  
* What’s a flash and when do you want to use flashes?  
A flash contains data which persists through the next http request. Its useful to display messages about the previous request to the user like error messages  
* Why do people say “HTTP is stateless”?  
On the server side, each request is handled the same way, the order of requests doesn't matter. If HTTP had state then the result of one request would change how the next request is handled.  
* What’s authentication? Explain.  
Authentication is proving the client is who they claim to be.  
* What’s the difference between authentication and authorization?  
Authorization is showing the right content to the right people. Authentication is verifiying the identity of people.  
* What’s a before filter?  
A method that checks a user's role before performing an action in a controller.  
* How do we keep track of a user once they’ve logged in?  
We give them a session which stores their user_id, and we check that user_id before performing various actions.  
* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?  
Nesting makes a child resource depend on a specific parent resource. A name space allows the same resource to be handled in two different ways. Namespacing is a good choice for having seperate behavior for different levels of authorization. Nesting is a good choice for representing a "has_many" relationship.  
* At a high level, what tools can you use to implement authorization? How would you use them?  
Sessions, before filters and namespacing. If a user tries to navigate to a route that is restricted (indicated by the namespace), use before_action to call a method that checks their session and verifies their level of permissions.  
* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?  
Enums map a word to an integer value. Rails has built some methods on enums which can serve as shortcuts and make the code more readable. The database needs to store an int and the model should declare `enum column: [values, ... ]`  
* What are some strategies you can use to keep your views DRY?  
Helpers and partials. Partials allow you to extract repeated code into a single file. It's useful for forms which can be used for both new objects and editing existing objects, or for displaying things in a consistent manner across multiple pages. Helper methods extract code from your views. Rails has some built in helpers for links, but you can define your own for many cases.  
