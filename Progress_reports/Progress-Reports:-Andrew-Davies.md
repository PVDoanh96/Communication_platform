## 10/21/2012

**What we said you were going to do this week.** This week I was tasked with writing up the rest of the architecture document in order to make it up to snuff by the eve of 10/22/2012.

**What we did this week.** I haven't made the document "up to snuff," but it's getting there.

**What we are going to do next week.** Next week I plan to help getting the prototype up and running, and if not that, then help with the presentation.

**Issues.** None that I can think of.

## 10/28/2012

**What we said you were going to do this week.**  This wasn't entirely clear.

**What we did this week.** 
* Completed the rest of the architecture docs and wrote up some more of the UI/UX (now 'up to snuff,' in my opinion).  
* Expanded a bit of the command line functionality for the section assignment (the sorter tool).
* Got to experiment a bit with unit testing.  Found out about the python "nose" tool (as well as general naming conventions for unit tests and where to put them in a file hierarchy).

**What we are going to do next week.** Next week I plan on getting settled on what issues need to be worked on, and who is going to be paired with whom so that we can hammer out the rest of the features intended for the first release.

**Issues** Not really an issue, but importing python modules from different directories is a bit of a pain.  It seems the best way to implement tests is to just put them in the same directory as the module with "_test" on the end of the name.

## 11/4/2012

**What we said you were going to do this week.** 

Enable login and registration for users.

**What you did this week.** 
* Completed login and registration.  A user's session is tracked via a cookie.  We also used the default django User model, since it has authentication built in.
* Remodeled directory structure.  The coupling of urls, forms, and views are now a lot more loose between apps (though there is some interdependency that can be removed).
* Confirmation emails are now enabled.  When a user registers with the website, if they haven't registered already, they'll be given an activation link.  Upon following the link, their account is activated depending on whether there is an activation linked to the person in the database.

**What we are going to do next week.**
* Creating groups.
* Email invites.

**Issues** None.

## 11/18/2012
**What we said you were going to do this week.** 

Enable user to user invites.

**What you did this week.** 
* Created the framework for user to user invites.
* Reformatted the way emails work (now everything is implemented with django's mass_mail function)
* Lists of emails can be sent to users to invite them to a group (not yet on the front end).  The registration basics on the back end are completed (though there is not yet an option for saying "I'm already a user on the website" and becoming a member of the group using a different account).

**What we are going to do next week.**
* Not sure as of yet.  I'm probably going to be working on some of the framework for the Inbox notifications and such.

**Issues** The code is getting a bit hairy as we've transitioned over to using AJAX and JSON for delivering data back and forth from the server.  Now code has been largely separated into different strange areas, making it difficult to extrapolate what's going on with certain functions, as the outcome of a function in any views.py is no longer explicit unless someone has knowledge of the underlying implementation in the JS that handles the returned JSON response.