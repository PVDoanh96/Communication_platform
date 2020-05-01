Introduction
------------

Bulletin is a collaboration tool for small, private groups. It enables anyone to quickly set up a space for private status updates and comments, which only the group members have access to, allowing quick and easy communication. As it grows, Bulletin will have more functionality to help groups get work done, like project agendas and task lists.

High Level Description
----------------------

### Background
One of the biggest issues in a growing company is communication among all levels of staff. The lower and more autonomous an employee is, the less direct communication they receive from other members of the company. Email has traditionally taken the place of direct communication in these cases, but falls short in many ways. Alone, email does not lend itself to mass directed status updates, multi-user collaboration, or specific information gathering. Social networks like Facebook and Twitter have revolutionized interpersonal communication, but the inability to separate personal data from workplace data results in them not being appropriate on the job.

Bulletin hopes to remedy this by providing a new platform for group communication. Influences are drawn from both social networks and email, as well as direct forms of communication. Like a physical bulletin board in a home or office, Bulletin allows users to post public messages and provide information to friends or teammates in the form of status updates. Status updates are quicker to write and easier to understand than emails, so in many cases will be preferred. The service is split up into private groups. Users can create groups for a specific purpose and post to it. Only other members of that group will see the posts. The point of this is to separate and organize feeds to show only information that is important at that time. Privacy and keeping information related to the topic of choice will allow Bulletin to fit right in in an office environment or any kind of project.

### Audience
Bulletin is aimed at any group or company that hopes to communicate more easily within the group and keep everyone informed about the status of the company or project. The service works best in small environments (3-50 people) but because of the customizability of groups, may be able to scale to even the largest companies or organizations.

### Alternatives
Public social networks such as Twitter and Facebook, as well as enterprise social network Yammer, all have a foot in this space. People do use these platforms for group updates and communication, but they are not well suited for this. All three of these platforms have one major problem. They are used as social networks. Information is not well segregated and important updates about projects can easily be lost in countless unrelated posts. Bulletin will not allow global posting specifically to prevent this. An overarching "Company" group might be created by the users to act as a general posting area, but it will have no effect on any other groups.

Email, as mentioned, is a well established alternative for company communication but has several drawbacks. Email is used for so many things, it has the same problem as social networks: information gets lost. Tags and folders may help separate information, but must be applied after the message is received, and by the receiver instead of the sender. It should be the other way around. The sender knows what the message is about, and should be the one to create a context for it. In Bulletin, the author must choose a group to post in, ensuring the message gets placed in the correct context. Group collaboration also falls short. Mailing lists and "reply all" buttons are an afterthought to platform. Replies get messy fast and adding users to a conversation is difficult at best. Bulletin solves this by hosting group conversations in a way that allow any user to be added and see the entire history of that group.

### Features of Bulletin
Any business or group will be able to benefit with the simplicity of Bulletin. To create the basic functionality of the platform, a few features are a necessity.

1. Login/registration
2. Creating groups
3. Editing groups
4. Viewing groups
5. Posting to a group
6. Commenting on a post
7. An inbox of recent activity on joined groups

Additional features, as time permits, will help Bulletin become more usable and robust.

1. File attachment
2. Mobile access
3. Highlighting or prioritizing specific posts
4. Tree-style comment system
5. Direct messages
6. Editing/deleting posts and comments
7. Project agenda
8. Task lists


Users and use cases
-------------------

We have a few types of users in Bulletin, with different levels of power. In this section we'll examine who they are and what they need to get done.

- *Group members* can log in, write posts, write comments, see posts in a group, switch groups, create a group, view inbox, log out.
- *Group admins* can also add users to their group, delete users from their group, delete their groups.
- *Site administrators* can do all of the above, as well as edit groups they do not own and remove users from the system.

### Scenarios

**Scenario 1: George**

George is a media editor at Fail Fast Productions. He works a graveyard shift because Fail Fast has insane clients that need to place orders at 2 AM and have a completed project by 10 AM. Only a few clients call this late, so he works alone. Since it is a very small company, most employees take on several roles, and he can pass off most projects to anyone who has time. Late one night a drunk fishing captain, upset about his last order, calls George demanding an invoice review. George tries to walk him through it, but the captain is belligerent and demands that he be called the next morning. George has to pass it on to someone.

Actor: George, a group member
Scenario: Group member writes a post
Precondition: George is a member of a group
Trigger: George wants to pass on information to the morning crew
Success condition: Post is made
Failure condition: Post is not made

1. George enters log in information to Bulletin
2. Info is verified and George is logged in
3. Bulletin displays George's Inbox
4. George enters the appropriate group screen
5. Bulletin displays posts from group, if any
6. George writes a note for his coworkers
7. George submits the post
8. Bulletin displays the new post

Exceptions: George can't log in, George's post is not recorded and not displayed

**Scenario 2: Debbie**

Debbie is an art director at Fail Fast Productions. Her boss demanded that she get a full page advertisement completed by this afternoon. Her first design was rejected since it didn't "pop" and there weren't any puppies in it. She needed to start from scratch. She decides to get help from her intern and recruit two other employees to find stock art of puppies. But she needs a way to keep everyone up to date on the design. She logs in to Bulletin and starts a new group for this project.

Actor: Debbie, a group admin
Scenario: Group admin adds users to group
Precondition: Debbie has already created the group
Trigger: Debbie wants to add three users to a group
Success condition: Users are added and can access group
Failure condition: Users are not added or cannot access group

1. Debbie logs in to Bulletin
2. Bulletin displays Debbie's Inbox
3. Debbie enters the group screen
4. Bulletin displays posts from group, if any
5. Debbie enters the group settings
6. Debbie chooses three names from a list, or adds additional emails
7. Debbie saves and exits the group settings
8. Added users are notified via their Inbox and can now access Debbie's group

Exceptions: Debbie can't access group settings, users are not available from list, users are not added to group, users are not registered on Bulletin

**Scenario 3: James**

Stepping outside the workplace, James is a student at University of Washington. One of his courses demands that he work with a group of six other students to build a software project in ten weeks. Needing a way to update all team members at once, they decide to make a group on Bulletin. The requirements are due in two hours and James is wondering if the project manager has turned in the file and updated the team on Bulletin. If so, it should be in his inbox.

Actor: James, a group member
Scenario: Group member wants to view new posts
Precondition: James is a member of the group
Trigger: James wants to check on the status of his project
Success condition: New posts made to group are visible in inbox
Failure condition: New posts do not appear in inbox

1. James logs in to Bulletin
2. Bulletin displays James' Inbox
3. James sees a new post by his project manager, mentioning the turn in
4. James clicks on the post
5. James is taken to the group screen, displaying the post and any comments

Exceptions: James' inbox does not display new posts, project manager did not make an update, James is not taken to group screen when he clicks on the post

**Scenario 4: Catherine**

Catherine is a friend of James. She is a UX designer and has agreed to give some feedback on the design that James' group has come up with. She'd like to join the group so she can ask questions when they come up. James' project manager, an admin of the group, sends her an invite. Luckily, since Bulletin is so popular, she has used it on other projects and has an account already.

Actor: Catherine
Scenario: User wants to be added to a group
Preconditions: Catherine has a Bulletin account, an invite has been sent
Trigger: Catherine wants to join in the group conversation
Success condition: Catherine becomes a member of James' group
Failure condition: Catherine does not become a member of James' group

1. Catherine receives an email, notifying her that she has been invited to a group
2. Catherine clicks the join link provided in the email
3. Catherine is brought to Bulletin
4. If Catherine is not signed in, she must first sign in
5. She is brought to the group page, and can view and make posts (in addition, the group now appears in her list of available groups on the left, and any new posts in this group will appear in her inbox.)

Exceptions: Catherine is not a member of Bulletin, Catherine is not added as a member of the group, Catherine does not receive an email invite


Feature Specifications
----------------------

Several main features must be developed for the minimum viable product. They are as follows, broken down by section. Priorities are either high, medium, or low.

**Login/registration**
- New users must be able to register for the service and create an account
	- Priority: high
	- Cost: 1.5 days
	- Release: 1
	- Issues: If OAuth is added later, may need to change our code
- Existing users must be able to log in and access their account
	- Priority: high
	- Cost: 1.5 days
	- Release: 1
	- Issues: If OAuth is added later, may need to change our code

**Creating groups**
- Any user can create a new group and become a "group admin" for that group
	- Priority: high
	- Cost: 1 day
	- Release: 2
	- Issues: None, hopefully
- The name of the group is editable
	- Priority: high
	- Cost: .5 days
	- Release: 2
	- Issues: None, hopefully
- Users can be added by any group admin (of that group) or site administrator to that group
	- Priority: high
	- Cost: 1 day
	- Release: 2
	- Issues: Must implement the invite system
- Group admins or site administrators can create other group admins (to that group)
	- Priority: high
	- Cost: .5 days
	- Release: 2
	- Issues: None, hopefully

**Editing groups**
- Group admins or site administrators can edit the name of the group
	- Priority: high
	- Cost: 1 day
	- Release: 2
	- Issues: Shouldn't be a problem with our model
- Group admins or site administrators can add members to the group
	- Priority: high
	- Cost: 1 day
	- Release: 2
	- Issues: Invite system must be implemented
- Group admins or site administrators can remove members from the group
	- Priority: high
	- Cost: 1 day
	- Release: 2
	- Issues: May be an issue if member is an admin

**Viewing groups**
- Group members can view all posts to a group they belong to
	- Priority: high
	- Cost: 3 days
	- Release: 1
	- Issues: Front end group needs the templates before they can start styling this

**Posting to a group**
- Group members can post to a group they belong to
	- Priority: high
	- Cost: 3 days
	- Release: 1
	- Issues: None, hopefully.

**Commenting on a post**
- Group members can leave a comment on a post that is visible to them
	- Priority: medium
	- Cost: 2 days
	- Release: 3
	- Issues: Requires posts to be working

**An inbox of recent activity on joined groups**
Note: Users will be presented with their Inbox upon logging in
- A list of notifications will be displayed
	- Priority: high
	- Cost: 1 day
	- Release: 3
	- Issues: None, hopefully
- Users will receive a notification if they have been added to a new group
	- Priority: medium
	- Cost: 1 day
	- Release: 3
	- Issues: Invite system needs implementing
- Users will receive a notification if groups they are a member of have new posts
	- Priority: medium
	- Cost: .5 days
	- Release: 3
	- Issues: Group posts or separate posts, TBD
- New post notifications will have a post count and authors
	- Priority: low
	- Cost: .5 days
	- Release: 3
	- Issues: Only if new posts are grouped together

**Invite system**
- When a group admin sends an invite, an email is sent to the user specified
	- Priority: high
	- Cost: 1 day
	- Release: 3
	- Issues: Only if new posts are grouped together
- When an invite is sent, if the user is a member of Bulletin, it will appear in their inbox


Other important features will be considered as time permits.

1. File attachment
	- A post may have a file of any type attached to it
	- If a post has an attachment, a link is shown to download the attachment
2. Mobile access
	- Site should be accessible and usable via modern mobile browsers
	- Users can make new posts and comments
	- Users can access groups and inbox
	- Users can create groups
	- Users can edit groups

A few features are on a wish list for future enhancements

1. Highlighting or prioritizing specific posts
  - Posts can have either no priority or high priority (no priority is essentially "low").
  - Users can set their posts as high priority.
  - A group will have a section at the top showing the recent high priority comments.
  - High priority comments will be removed if they have either been handled (designated by the user who posted the comment) or explicitly removed from the "recent high priority posts" list atop a specific group page.
2. Tree-style comment system
  - Site would display a sort of "tab" space between different comments.
  - Comments of replying to a specific post would all be on the same tab level.
  - A line would be shown leading downward from the root comment to make it easy to follow.
  - A "view more" options would be applied to especially deep nests of comments (totalling a magnitude of 15 or more comments for now (will likely change during testing).
3. Direct messages
  - User will be able to recieve private messages from other users (separate from, say, a char system).
  - Private messages will be shown in the receiving user's inbox.
  - Receivers of private messages will be able to reply to private messages similar to email, with a "RE:" header, and a copy of the original PM indented at the bottom of the newest PM if they so choose.
4. Editing/deleting posts and comments
  - User will be able to hit an "edit" button on their posts or comments.
  - An edit history will be visible to the editor, as well as to other users.
  - User will be able to delete their comment permanently from the comment tree (or delete their post).
  - If deleting a post, all subsequent comments on said post will be deleted.
5. Project agenda
  - User will be able to add items to the agenda if given permission by the group admin, as well as deadlines outlining different milestones of a project.
  - Project agenda will be shared with other users inside of the group for which is was created.
  - Project agendas will be specific to their respective groups.
  - User will receive updates according to dates outlined in the agenda as per their settings, which, for now, will be specific to each event in the agend.
  - Users that have not created certain events on the agenda will receive inbox updates as other users append to said agenda.
  - At the admin's behest, events can be added and removed from the agenda.
  - Events can also be added and removed from the agenda by Users if the group admin so permits.
6. Task lists
  - User will be able to create a private task list (similar to the project agenda, but without public group visibility).
  - User will have the option to add a deadline date for the task.
  - User will have the option to get a notification for the task if it has a deadline.
  - User can choose whether to prioritize tasks based on numbers.  Priorities of lower number will show up higher on the list.
  - User can, of course, add and delete tasks at their own behest.

<a id="user_experience"></a>User Experience
---------------
[[UserExp.png]]

**Login**

Upon opening the page, if the user doesn't have an active session, then the login page will appear.  Here, the user will be shown the title of the website as well as a button that will allow them to log in with Google.  This will be the center of the page when coming in, taking up a small amount of screen real-estate and, in most cases (since Google likes to keep active sessions alive as long as it can), this will allow quick and easy access to the site.

**Logout**

Logout will be as simplistic as login, and will only involve hitting the logout button at the top left corner (this will not, however, log the user out of Google).

**Group Tab**

Interaction within the group tab will largely stay within the group tab.  This interaction will include looking at posts (scrolling down will take the user to older posts), and responding to posts either via the like button or the reply button.  If the reply button is pressed, then the user will be able to type in their response up to the character limit (the user will not be allowed to submit comments beyond the character limit (which is, for the moment, 1000 characters;  the character limit may go up or down depending on the server performance exhibited testing)).

**Inbox Tab**

From the inbox tab, the user will be able to view the most recent (as well as older) posts in different pages.

**Group Create**

The group create section will be largely similar to the group edit.  When they are finished editing the new group, they will be taken to the group's tab upon hitting the "Save" key.  If they hit cancel, the group will not be created, and the user will be taken back to the top group in the list of group tabs.

**Group Join**

A user cannot explicitly join a group.  They have to be invited to a group.  And upon accepting the request (through email and/or in their inbox if they are already registered), the user will remain in their login page and the group will be added to the other existing group tabs.

### Email Group Invite UX

[[InviteRegistration.png]]

When a user receives an email invite, Bulletin will send a link to the
recipient's email address, allowing them to follow the link and complete their
registration.  Upon following the link, if the recipient is already a user on
the website, or is a user that hasn't yet activated their account, then the
recipient's account will be activated if necessary, and they will be redirected
to their inbox page, and they will have been added to the group in question.  If
the recipient is not a user on the website, then they will be taken to a form
wherein they will complete their registration for the website if they so choose.
If, however, the user is already registered on the website, but with a different
email, they will have the option to login and be added to the group with this
separate email.

### UX Prototype

A simple UX prototype can be found [here](http://invis.io/QP7SQHX6), although keep in mind some of the diagrams are a little out-dated.  For example, the "Join a group" button will no longer be used.

User Interface
--------------
Bulletin users will spend time on a few different screens. The look and feel will be consistent throughout and these mockups are only an example of what the interface might look like.

###Inbox View
[[inbox view updated.png]]
When a user logs in, they are presented with an inbox view. This is the main notification center. The inbox consists of any received private messages, invites to groups, and activity in groups the user is a member of. A user can see, at a glance, activity in any groups or projects they are involved in.

###Group View
[[group view.png]]
After a user is invited to a group, it will be accessible on the left, under Inbox. This screen shows the posts to a group. They take on microblog like flow, with newer messages appearing at the top, and comments to posts descending below the post.

###Group Settings View
[[group editing view.png]]
If a user is a group admin, they may edit the details of the group including the group name, the group members, and the permissions of members. When a new group is created, a similar screen is displayed.

###Design Assets
Font stack: 'Helvetica Neue', Helvetica, Arial, sans-serif;
Iconography: Glyphicons from Twitter Bootstrap
Graphics: Bulletin logo, default user avatar
Color scheme: TBD, but beginning with #DDD for the borders, #EEE for some backgrounds, and #08C for active links.

Product deliverables
--------------------

Bulletin is a consumer facing web application. It will be accessible by most major modern browsers on most operating systems. Based on preliminary design choices, a minimum compatibility list follows. This list is subject to change.

<table>
  <tr>
    <th>OS</th>
    <th>Browser</th>
    <th>Version</th>
  </tr>
  <tr>
    <td>OS X</td>
    <td>Mozilla Firefox</td>
    <td>5+</td>
  </tr>
  <tr>
    <td>OS X</td>
    <td>Google Chrome</td>
    <td>14+</td>
  </tr>
  <tr>
    <td>OS X</td>
    <td>Safari</td>
    <td>5+</td>
  </tr>
  <tr>
    <td>OS X</td>
    <td>Opera</td>
    <td>11+</td>
  </tr>
  <tr>
    <td>Windows</td>
    <td>Internet Explorer</td>
    <td>7+</td>
  </tr>
  <tr>
    <td>Windows</td>
    <td>Google Chrome</td>
    <td>14+</td>
  </tr>
  <tr>
    <td>Windows</td>
    <td>Mozilla Firefox</td>
    <td>5+</td>
  </tr>

</table>

In addition to desktop browsers, mobile access is a high priority and the site should be accessible to modern mobile browsers. The principles of responsive web design should be followed.

Product Metric
--------------
Our "real" metric will be active monthly users. We will gather this data via Google Analytics (http://www.google.com/analytics/). This should provide a decent measure of how useful the site is.

For grading purposes, our project should be considered successful if each release completes the features listed in the Schedule, as these are the most vital features for Bulletin to be useful.
