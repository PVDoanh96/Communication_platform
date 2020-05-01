Modules
-------

(System data flow)
[[system_model.png]]

**Email Manager**

This is not visible to the user, but the interaction they have is to receive email updates from the website for various things like new posts, comments, and invites.

* We will use django's implementation, django.core.mail.send_mail.
* https://docs.djangoproject.com/en/1.4/topics/email/#module-django.core.mail

**Site Administration**

Site administration is invisible to the user, as this is used for editing and managing info within the various models on the page.
* We will use django's implementation, django.contrib.admin.
* https://docs.djangoproject.com/en/1.4/ref/contrib/admin/

**Session Manager**

SessionManager is invisible to the user, as it simply handles their logging in as well as their session info.

provides the following methods (for the dev view):
* + logIn(email:String, hashed_password:String):token
	* if given email and password combination are valid and a session doesn't already exist for the user:
		* generate a random session token for user
		* link with IP address of user and user id
		* store in database model 'Session'
		* save a session cookie in client browser
		* return session token
	* otherwise return null value to signal failure
* + logOut():void
	* delete session cookie on client
	* remove session entry from 'Session' model
* + currentSession():User
	* if session is valid, return 'User' model
	* else, return null value
* - generateToken():string
	* create a random token that doesn't already exist in the database and return it
* - isValid():bool
	* verify if current session token (from cookie) and stored IP address match

**Post Manager**

Create a PostManager for a given 'Group.'  The user would see this as part of the main page for any group, and would handle their posting of posts (roots of comment groups) and comments (children of the root comment).

provide the following methods (for the dev view):
* + PostManager(group:Group):PostManger
* + addPost(author:Member, message:String)
	* verify author is a member of the Group
* + addComment(author:Member, message:String, post:Post)
	* verify author is a member of the Group

**Invite Manager**

Create an InviteManager for a given 'Group.'  The user would see this as part of the invite page (see URI).  Handles inviting people to groups via email (the email sends a link so they can create an account).  If the user already has an account and they're invited, the methods will, of course, perform differently.  When the user doesn't have an account, they will be tasked with creating one upon opening the link sent in their email.

provide the following methods (from the dev view):
* + sendInvite(email:String, from:Member)
	* use django's send_mail to send an invite to the given email
	* create invite for group of given 'Member'
* + deactivateInvite(invite:Invite)
* - generateKey():string
	* return a random string to act as a key
	* verify key doesn't already exist

### Design
[[ModelViewTemplate.png]]

The modules will be designed (apart from the major ones listed above) adherent to the Model, View, Controller pattern (though because of Django, it will now be referred to as the Model, Template, View, pattern, wherein Model is the same, but Template is essentially equal to View, and View is equal to Controller).  The controllers within the view.py section of each module will handle the data that is grabbed from the server before sending the data to the template, which will handle how it is displayed on the screen.

The [database schema](#database_schema) will outline essentially how the classes will relate to one another (as Django's models essentially reference each other as a Python equivalent of a high level database schema, albeit with more restrictions on the type of data which can be stored, and how elements link to one another).  For the most part, the classes within the system will be independent, apart from the knowledge of their interconnectedness (more on this in the overall description of the [database schema](#database_schema)).

Pages with similar layouts (for example, the create group and edit group pages), will be able to inherit from a root template when creating a view for the user.

[[template inheritance.png]]

<a id="database_schema"></a>Database Schema
---------------

[[models_relations.png]]

The database schema, as outlined by the UML diagram, shows how all of the clases are related as django models.  The arrows showing that a class is contained within another class have a two way meaning.  The class that is within another class (i.e. a Member being within a SeenBy model) has implicit knowledge of the container class.  For example, the Member will have a set containing all of the SeenBy models that reference it.  This is how many of the connections between classes that aren't explicit within the UML diagram are able to be established within the framework we're using (Django).

**Comment**

  This contains a comment.  A comment is different from a Post in that it is strictly a reply to a Post, and cannot be the root of a series of comments like a Post can.

**Group**

  This contains information about a group on Bulletin.  Groups contain numerous members and must have at least one admin, or else they are invalid (the "Active" field will be false).  Since a group is related to a Member via a Foreign Key relation, the Group will have access to all of the members contained within it.

**Member**

  This contains the information relating a User to the Group they have joined.  Since the user is linked to the Member via a foreign key, the User will have view access to all Member models they are connected to and thus know all of the memberships they are associated with.  The same goes for Groups (they will know who all of there members are, as well as which ones are administrators).  A Member also has knowledge of any posts they have made.

**Post**

  This contains a post within a group.  A post is the root of a series of comments.

**Invite**

  Contains information pertaining to an invite from a member to a particular email.  The invite will be valid for a certain period of time, and will be deactivated by either expiring due to time, or by a user having accepted the membership request.

**SeenBy**

  This contains a Post and the information about the members that have seen it.

**Session**

  Contains a session for a specific user.  This is so that the user's session remains secure whilst they are logged into bulletin.

**User**

  This contains the information about a User and their membership to the bulletin web app.

##URI
root: www.bulletinapp.net

The URI for bulletin will be similar to that shown in the [User Experience section](https://github.com/caylan/Bulletin/wiki/Requirements#user_experience).

###Do not require an active session:

**/** 

Login

* http:get - ask for login credentials
* http:post - verify credentials, redirect to /inbox on success

**/register**

Registration page

* http:get - ask for information
* http:post - create user, redirect to /inbox on success

**/about**

All about Bulletin

###Require an active session:

**/inbox**

Homepage

**/settings**

Personal settings

**/group/create**

Group creation

**/group/{grpid}**

Group feed, must be member of group to view

**/group/{grpid}/invite** 

Create and send group invitations, for group admin

**/group/{grpid}/settings** 

Manage group settings and invites, for group admin

###Administration:

**/admin - Django’s built in admin site**


Tools and Runtime
-----------------

### Tools

**1. Programming Languages**

For the backend language we decided to use Python and the [Django](https://www.djangoproject.com/ "django") framework. We were contemplating between Ruby and Python as they are both currently popular in the industry, but we chose Python because our group has more combined experience with it. Django is the standard Python web-service framework so it was logical to use it.

We decided on Ajax for the frontend, using Twitter Bootstrap and Jetstrap to speed up the process of generating a cross-platform UI. Messing around with CSS and HTML to make things consistent is a big time sink, so Bootstrap should speed that process up, and we decided on Ajax since our website is a web app, and Ajax (with the help of jQuery) will help make a rich and cross-browser compatible web experience. No Ajax alternatives were considered as it is the defacto standard for web apps, and our group already had experience programming with Ajax in JavaScript frameworks like Prototype.

Django also comes with its own quirky markup syntax for templates. It is similar to python, but due to the inability to track indentation consistently across execution, the syntax had to be changed accordingly.  The templates are used to create dynamic HTML pages that will be sent to the user.  The syntax for them can be found on the [django template page](https://docs.djangoproject.com/en/dev/ref/templates/).  An example looks as follows.

    {% autoescape on %}
        {{ body }}
    {% endautoescape %}

**2. Editors**

We do not have a standard IDE that everyone will have to use, so long as each engineer’s favorite IDE works well with Git/GitHub and has modules that will debug python/ajax programming then it should work. Komodo Edit is an IDE to default to if anyone in the team is at a loss for what environment to use. We didn’t want to force an editor as it wasn’t necessary and productivity would go down in a foreign editing environment.

Given Python is rather strict with indenting via tabs or spaces, we have decided that to be consistent, the only stipulation on editors will be to adhere to using four spaces per level of indentation while editing Python, as outlined in the [Python style guidlines](http://www.python.org/dev/peps/pep-0008/#indentation "Python Indentation").  

**3. Version Control System**

Git and GitHub are required to use as our version control system, so no alternatives were considered.  Github also has a very robust issue tracker which we will use for dealing with the bugs that can (and will) show up later on in development.  Furthermore, given we are going to deploy on Heroku (see [item 8](#deployment_system) in the list), the tools Heroku provide allow us to seemlessly send changes from git to Heroku, since Heroku's deployment system is built on top of Git.

**4. Wiki**

We are using GitHub’s wiki to consolidate where our team is keeping its information. No alternatives were considered here because keeping the wiki in a different place didn't justify leaving the benefits of using a single ecosystem.  Furthermore, the markdown language the wiki uses is very simple and easy to read in both the browser, and in a text editor.

**5. Bug Tracking System**

We are using GitHub’s issue tracker for bug tracking to consolidate for the same reasons as the wiki.

**6. Test System**

We decided to use Django’s implementation for testing to keep our methods of testing within the environment itself, and then write the tests as we go for the javascript files. For using the test system in practice, after writing our own tests as we go, we will exchange methods that we wrote with other engineers in the same environment (backend, frontend) to blackbox test.  Django implements unit testing through a module called unittest, which can be extended to any classes that will contain unit tests.

For (a simple) example:

    import unittest

    class MyTest(unittest.TestCase):
        def testBasic(self):
        a = ['billy', 'steve', 'gaston']
        self.assertEqual(some_function(a, 0), 'billy')
        self.assertEqual(some_function(a, 2), 'gaston')

Would work as a unit test for "some_function."  The other alternative (embedded doctests, in which test cases and results are written out as if in the python REPL) seemed unintuitive (despite how cool the idea) compared to the conventional unit tests.

For automated testing we will use [nose](https://nose.readthedocs.org/en/latest/), which will make testing across various sections of the entire testing suite quite easy.  The reasoning behind this is because in order to make testing simple and easy between modules, rather than having one dedicated testing directory with references to different packages (like Java, for example), the tests will be contained within the directory of the module itself.  So, in order to run tests across all modules, we would need to use nose, which automates this process with efficacy.  Nose also recursively runs through all sub modules to run tests.

For example, this code would run all tests contained within the two separate test directories 1, and 2:

        nosetests -w /path/to/test/dir/1 -w /path/to/test/dir/2

**7. Debuggers**

We will use the [PDB](http://docs.python.org/library/pdb.html) system for python debugging, as this is the defacto standard for debugging python code.  As another robust alternative, we may choose to use [IPython](http://ipython.org/), as the tool contains many useful additions to the simple python shell.  PDB supports many necessary debugging features, such as conditional breakpoints, line-by-line stepping, and tracking variables accross program execution.  In addition to this, popular Python IDEs come with debuggers, and if this proves to be useful for an individual engineer, then they can use exclusively that debugger if they so choose.

<a id="deployment_system"></a>**8. Deployment System** 

We are going to deploy on [Heroku](http://www.heroku.com/ "heroku"). Heroku has the tools to use a github repository to host the files on a free subdomain.  Heroku also offers a virtual environment on which we can install python apps without needing root privileges.  We simply supply a requirements.txt, and heroku installs everything marked.

On Heroku we can deploy the django app using the low-quality built-in django server for development purposes, but when we want to scale up to full deployment, we plan to use [GUnicorn](http://www.gunicorn.org/) which is a simple yet robust python server based off of the Ruby Unicorn project (which, using the virtual environment Heroku supplies, can be installed with the rest of our tools).

Heroku uses Ubuntu 10.04 to work with any Python deployed on their server, so we will be using the same. Heroku also uses Postgres for data management, so we will follow suit and use their service. Heroku will take care of the other runtime system information, and since we are students we get free runtime hours to deploy on for the quarter. We made the choice of Heroku due to our research that it would streamline the process as much as possible. Since Heroku is free (to us) and can interface with GitHub easily and host our files and database, it seemed like the best choice in comparison to WebFaction and the department machines.

**9. Schema Migration** 

We will be using [South](http://south.aeracode.org/ "south") to handle database schema migrations.  This allows us a simple way to add changes to Django models without having to worry about maintaining compatibility with old elements already in the database.  South is capable of being either initialized along with the app during the initial deployment, or added later on down the line.  Since South was built essentially for Django, we also won't have to worry about the database implementation.

### Topology

[[topology.png]]

### Technology Stack

[[TechnologyStack.png]]


Process
-------

Bulletin will be created and released via evolutionary delivery with milestones defined at each release deadline -- a hybrid of the the feature-based and train process. We will also consider using the development technique of pair programming (http://en.wikipedia.org/wiki/Pair_programming).  Each release cycle will be two weeks:

1. Implement initial prototype
	- Requirements should be solid at the end of this cycle.
	- Feature design should be solid at the end of this cycle.
	- Deployment of the web app should be done at the end of this cycle, or the beginning of the next.
2. Prototype refinement/feature addition
	- Implementation of core features should be completed during this cycle.
	- Decide on which additional features to attempt and begin implementation.
	- Testing.
3. Complete and release prototype
	- Decide which additional features can't be deployed and finish implementation.
	- Close requirements.
	- Close features.
	- Testing.

###Testing

Testing will be done concurrently with development and rolled into an evolving test suite. Developers will test their own code (basic quality assurance to ensure functionality) and review others' code (programmer quality assurance to ensure readability and sane design).

Organization 
------------

[[OrgChart.png]]

Caylan acts as the product owner and general team lead. He is responsible for assembling and maintaining the requirements, overseeing the individual groups' work, reaching successful releases, and solving any techinical or personal issues that arise within the groups.

Despite the apparent rigidness of the organization chart, any team member can be a go-between depending on how much work needs to be done in a given area.  Each category is more of a specialization, where we expect the person to know as much as possible about their area of the project.  There are, however, some "official" go-betweens that will need to know enough about their respective areas (not necessarily extensive knowledge) in order to, hopefully, prevent any movement of back-end developers to front-end or vice versa.  Go-betweens will likely update as the project continues and we have better team organization, but for now the Go-betweens will be Yoong for project management and front-end development, and Andrew for back-end and front-end development.

Yoong is the product manager. He organizes the group meetings, reports to the TA, and monitors the progress of the individual groups. He estimates the cost of development and, with help from Caylan and feedback from the groups, will adjust the feature set as needed.

The back end group is made up of Kyle, Andrew, and Brian. Together, they will self organize and create the modules and tests needed for the management and display of data within the system.

The front end group is made up of Ivan and Peter. Together, they will self organize and write the code and any tests needed for the visual design and user experience of the site.

Weekly progress reports will be sent by each member to Yoong, and any issues that arise will be sent to Caylan.
