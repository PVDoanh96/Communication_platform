## Bulletin

### Overview
The second release of Bulletin brings a new set of features. Users can now create groups and invite others to their created group(s) via email invitation. Users can also reset and change their password. There have been some visual tweaks, as well.

### Functionality
* **Register** Visitors can register to access the site. Visitors are asked for their first name, last name, email and password. Visitors can't make multiple accounts under the same email (unique user emails). Once visitors have filled out the registration form, a verification email is sent to the provided email address, providing a link to activate the account.
* **About** Visitors and users can click on a link to learn more about Bulletin from the login page.
* **Sign in** Registered users can login via the main page. They are asked to provide their email and password.
* **Password reset** Users can now reset their passwords. If they incorrectly enter their email or password, the login page will inform them of that and ask if they want to reset their password. Should the user agree, the user will be directed to input his/her email address associated with the account. An email will be sent to that account with a generated password, which can later be changed.
* **Password change** Users can change their password. Once logged in, users will find a drop-down menu in the top right-hand corner of the screen. There are two options there, Change Password and Logout. If the user selects Change Password, a window will appear prompting for the current password and the new password to which the the user wishes to change.
* **Inbox/groups** Users that have signed in can view the inbox (a future release), and groups that they are a member of. In each group, users can view posts and comments made by other members to that group.
* **Group creation** Users can now make new groups. Users will be asked to name their group.
* **Group invites** In order to become a member of a group, a user has to have either created a new group or have been invited to a group. Group invites are managed by the creator of the group, and sent to emails listed by the creator. The assumption is that all collaborators in a group know each-other well, and need no knowledge of the entire database of users (Feature possibly delayed).
* **Post** Users can make text posts to groups that they are a member of.
* **Comment** Users can make comments to posts in groups that they are a member of.
* **Avatar** Users with an email associated with a gravatar (https://en.gravatar.com/) account will automatically use the gravatar avatar.

### Exceptions
Some things that might not be working:
* Some minor design aspects may not work as well in IE, but functionality is good.
* If a visitor correctly guesses a user's email, the visitor can cause the user's password to reset.
* Registration emails can be delayed for prolonged periods of time (email isn't always immediately sent).

### Accessing the release
You can visit the website at http://www.bulletinapp.net/