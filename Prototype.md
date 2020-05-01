The prototyping stage for Bulletin is an exciting one. It’s been about three week into the project with most of our efforts being poured into planning and preparation. Now we’re at the point where we find out if the ideas that seemed to work conceptually actually work. The plan is to break down the application into individual parts that can operate alone, separated from the others, and get them roughly working so that by the first release, we can bundle them all together and have a *whole, roughly working, application*. For the first week of prototyping we focused on the following:
* [Posts and Comments](#posts_and_comments)
* [User Management](#user_management)
* [Front-End Experience](#front-end_experience)

###<a id="posts_and_comments"></a>Posts and Comments

The ability for a user to make posts and have other users from the same group write comments to those posts is one of primary features that makes our concept of a “Group” work, as far as communication and interaction among users goes.

What the current prototype currently allows for is for anyone to make a post for a certain group (group1 or group2) and have them show up to the public. Anyone can also view comments, however, for the prototype, only the site admin can add comments. Posts are sorted by newest at top, but comments in the opposite order. 

###<a id="user_management"></a>User Mangagement

Any webapp that personalizes to a user requires a system for authentication. Our app is no different. In the end, we will need to associate users to groups, sessions, posts, comments, seen-bys, and group invitations. So far, for the prototype, we have been able to implement registering new users and assigning them sessions.

Implementing the rest will probably be one of the more time consuming portions of this project and therefore split among different releases.

###<a id="front-end_experience"></a>Front-End Experience

While a barebones UI is needed to confirm that the user manage and posts/comments are working, it is nowhere near the experience that a user needs when they use a webapp.

Therefore, implementing a front-end that approximates the finished product enough was necessary so that an equatable user experience can be felt while using the prototype. Built on top of the templates that served the barebones testing information to the user, this front-end prototype presents the user a direction on where we want to take the product.