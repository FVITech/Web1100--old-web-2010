Javascript WEB 2010
==============

Learning JavaScript is an essential part of being a Web Programmer.  It is the very first programming language you will learn as part of this course of study.  In this course you will learn the history and evolution of JavaScript, syntax, data types, variables, operators, literals, conditions and comparisons and arrays and loops.  Following this initial section students will learn objects, functions, events and the basics of cookies and debugging.  Additionally students will learn the browser object model, and JavaScript HTML document object model as well as synchronous JavaScript and XML, and JavaScript object notation.  Students will also gain an introductory understanding of frameworks and their applied uses.

##Day 1

Deep dive of jQuery through the treehouse jQuery basics course. By the end of this class, students will know how to: use compound jQuery selectors, attach events to DOM elements,  traverse the DOM tree, iterate through element sets, modify the inner html of DOM elements by appending, replacing or prepending, and add attributes to DOM elements. jQuery function chaining is also discussed. As far as structure, students also get to see the technique of having an invisible overlay (display:none) which gets made visible when certain elements are clicked (lightbox). Students are also exposed to mouse events through the jQuery drawing app tutorial.

##Day 2
Project work: build a lightbox of your own with your own styling and your own pictures, from scratch. The lightbox can be added to one of the sites they have worked on during a previous unit, or picking a template from html5up.net. Hacker points: make the lightbox position the image element with a margin-top which depends on the scroll position of the page (so that it's not one of those shitty lightboxes that you have to scroll up or down to see), and add a transition to the lightbox element.

##Day 3:  
We will talk about the concepts covered in chapter 5 of eloquent javascript. Abstractions. When we talk about foreach, replace the gatherCorrelations concept with a simple 2D array with "rows" and "cols" used as variable names within the traversal.

Define higher order functions - functions which work with other functions as parameters or return functions.

Expand on the f.apply syntax in the transparentwrapping function.

Recap on filter, map reduce.

Place special emphasis in "The Cost" section.

####TODO:
Pick specific codewars katas for noob and medium skill levels. The instructor will guide students through completing those katas while emphasizing the importance of exercises like these in interview prep. Each student must complete at least 3, preferrably using 2d arrays, filter, map, reduce, foreach, or function currying.

##Day 4:
The first half of the class is discussion about servers, and an implementation of a simple hello world server on node. The second half is a talk about sessions and scaling. We open the lecture with a discussion of web app server architecture by showing these videos:

https://www.youtube.com/watch?v=e4S8zfLdLgQ
Put into context: Every link, script, img tag generates a separate request. The original request generated by your typing a url or clicking a link spawns a cahin reaction after it gets the html and fires off a ton more requests. That's why many modern devs have workflows which concatenate and minify all their scripts and stylesheets before deploying.

https://www.youtube.com/watch?v=FTAPjr7vgxE
Make sure to explain that the definition of servers is very fuzzy. A server is no longer really just a machine. It can be and usually is a program.

We then demonstrate the functioning of apache by having students log into their digitalocean space, edit their pages right as they sit on the web server and view changes in the browser.

Now we show how web application servers work. We fire up a node server and create three basic routes using express. The first route is just a hello world route and the others demonstrate request parameters and query strings. The query string is just the POST body.

--- break ---

We start off with explaining the concepts of authentication and authorization, and how they are necessary within the context of any web app such as twitter. Login form -> post request -> server -> db -> server -> bifurcated path depending on whether credentials were valid -> response -> browser

Then we explain http sessions as detailed in here: http://machinesaredigging.com/2013/10/29/how-does-a-web-session-work/
Key points:
1. HTTP is stateless. Respond to request and that's it, no information about anything that happened before.
2. I could send the username with every request but if I did that then anyone who knows your username can see your profile and so on
3. So I could also ask for username and password with every request but that would be a pretty horrible solution too because then nobody would use the internet
4. So that's where sessions come in.
	..* After you log in one time, the server creates a new session id with some info about your session (at least your username) and saves it somewhere  
	..* Show and explain :  
	..* ![alt text][logo]

      [logo]: http://machinesaredigging.com/blog-mad/wp-content/uploads/2013/10/session_cycle.jpg "HTTP Sessions"  
	..* So your user needs to be sending the session id every time they send a request in order for the server to know they are authenticated. Three ways to send session id:
		....* Query string
		....* Cookie
		....* Request header
	..* Session management is a feature of the server, you usually need to activate it.
	..* Logging in is not the only use of the session. In the olden days you could use the session to store data about like a form that posted or something like that, so that you could use this data to render content.
	..* That's why sometimes if you were browsing the web and sent a link to someone they'd get an error.
	..* Another way to implement sessions: transferring all session data in an encrypted way back and forth every time, storing it in a cookie or in localstorage in the user's browser.

5. Then we talk about the scalability drawbacks (as it pertains to sessions). We start by recapping what scalability/scaling is. Then we talk about load balancing, new VMs, loss of data during transmission (now you have 2 sessions),  and with some implementations of sessions (ie memory usage) when the app restarts then all user sessions are lost, which can start a spiral of issues when they all hit the db to log in at the same time.  
6. Furthermore, there can be memory leak problems if you don't close and destroy your sessions manually.  
7. Usually sessions are closed when you close your browser.  
8. In every back end framework you are going to have slightly different options when implementing sessions.  
9. Recap: sessions can be stored in server memory, database, and also in encrypted cookie/localstorage data that the user has to send with every request.  
10. Another solution: token based authentication., which we explain tomorrow.  
11. Further reading on sessions, including how to create memory stores and db stores:   http://expressjs-book.com/index.html%3Fp=128.html
12. Practical, easy to follow examples on implementing sessions:  
http://blog.modulus.io/nodejs-and-express-sessions


Other links we could discuss, depending on how the class receives the above: Database scaling:  
http://www.rightscale.com/blog/enterprise-cloud-strategies/architecting-scalable-applications-cloud-database-tier  

Stateless authentication:  
https://scotch.io/tutorials/the-ins-and-outs-of-token-based-authentication

Rest of the day, if there's any time left, is codewars problems.

##Days 5-6:
These lectures will be a brief but intense applied guided practice exercise. Students will develop an authentication scaffolding with express.js under the instructor's guidance.

##Day 7:
Students are charged with creating a membership website with their resume emailer or any other project they've made, using the authentication scaffolding developed in previous days.

##Day 8:
Assessment: Quote of the day. Example finished version: velozmontero.fvi-grad.com/quote
TODO: Add a challenge mode for students who have been around for a while. Maybe such students can do the quiz app instead.

##Day 9:
Build your own scrolling effects (elements that fade in as they come into the viewport) with 2 lines of jquery and using the "data" construct. The day's task is then to add such scrolling effects to a site the students have previously made or to a template from html5up.net

#Days 10-12:
Lecture content is the "this" construct object and how to use it in the context of callbacks (cache it with a variable named self), event delegation and what it's for (when you bind events to elements that don't exist yet), jsonp, and the concept of APIs. We introduce the wikipedia API and we start the Wikipedia visualizer project, which is meant as a final asssessment.  

Students should understand that for the wiki visualizer, they can build their api requests through a gui tool wikipedia has. It's called the wikipedia api sandbox (https://en.wikipedia.org/wiki/Special:ApiSandbox) You also need to make sure that they remember to put callback=? As part of the query string, and when they build the api request, they need to use the generator called search, and up top they need to have the property set to extracts so they can get extracts of the page. Finally, extracts to multiple hits only work if you have the exintro property checked.  

```javascript
$.getJSON(
"http://en.wikipedia.org/w/api.php?action=query&prop=extracts&format=json&generator=search&gsrsearch=julio&callback=?",
function(resp){
	for (var x in resp.query.pages){
		console.log(resp.query.pages[x].extract);
	}
}
);
```
